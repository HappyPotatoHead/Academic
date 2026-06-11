# DynamoDB

## Creating Table

Click create table

![[dynamodb_console_front_page.png]]

Insert table information:

1. Table name
2. Table primary key (_dubbed partition key_)

![[dynamodb_create_table.png]]

Repeat this twice for ClassSchedule(classId) and OccupanyEvents(classId)

# Dashboard For Management

## Setting Up Database For Querying

### Lambda

#### IAM Role

Navigate to IAM dashboard

![[dashboard_iam_global.png]]

Navigate to the role section and press create role.

![[roles_iam_global.png]]

Select lambda under use case and click next.

![[create_role_iam_global.png]]

Select these permission:

1. AmazonDynamoDBFullAccess_v2
2. AmazonS3FullAccess
3. AWSLambdaBasicExecutionRole

![[choose_permission.png]]

Give the new role a name and a description.

![[name_desc_role.png]]

#### Lambda

Navigate to the lambda dashboard and click create function

![[lambda_dashboard.png]]

Insert or select function information:

1. Name
2. Runtime
3. Architecture

Select Use an existing role and select the newly created role. Click create function.

![[create_function.png]]

Navigate to the newly created function and insert the following code.

![[dynamoDBtoS3Exporter_functions_lambda.png]]

```javascript
import { S3Client, PutObjectCommand } from "@aws-sdk/client-s3";
import { unmarshall } from "@aws-sdk/util-dynamodb";

const s3 = new S3Client({});
const BUCKET_NAME = 'utility-classroom-data-lake'; // Your bucket name

export const handler = async (event) => {
	for (const record of event.Records) {
		if (record.eventName === 'INSERT' || record.eventName === 'MODIFY') {
			const newImage = record.dynamodb.NewImage;
			// Use the unmarshall function directly on the NewImage object
			const recordData = unmarshall(newImage);
			// Extract the table name from the event source ARN
			const tableName = record.eventSourceARN.split('/')[1];
			// Construct the S3 Key (file path) using the table name as a folder
			const s3Key = `${tableName}/${recordData.classId}/${Date.now()}.json`;

			const params = {
				Bucket: BUCKET_NAME,
				Key: s3Key,
				Body: JSON.stringify(recordData),
				ContentType: 'application/json'
			};

			try {
				const command = new PutObjectCommand(params);
				await s3.send(command);
				console.log(`Successfully uploaded to S3: s3://${BUCKET_NAME}/${s3Key}`);
			} catch (error)
				console.error('Error uploading to S3:', error);
		}
	}
};
```

Click on the add trigger button and select trigger to be DynamoDB.

![[trigger_lambda.png]]

Repeat this for the other two tables.

### S3

Navigate to s3 bucket and press create bucket

![[s3_dashboard.png]]

![[create_s3_bucket.png]]

### AWS Glue

#### IAM Role

Create a role with these permissions:

1. AmazonS3FullAccess
2. AWSGlueServiceRole
3. CloudWatchLogsFullAccess

![[s3_crawler_iam_role.png]]

#### AWS Glue

Navigate to the crawler section of the AWS Glue

![[glue_dashboard.png]]

Create Crawler. Provide its name and description.

![[create_crawler_name_desc.png]]

Select the Classroom data lake as the S3 source.

![[data_source_crawler.png]]

Select the created IAM Role

![[crawler_iam_role.png]]

Create a database and table name prefix to store the output. Set the schedule according to preference.

![[crawler_config.png]]

Repeat these steps for ClassSchedule and OccupancyEvent

### Querying the database

#### IAM Role

Create an IAM role with these permissions:

1. AmazonAthenaFullAccess
2. AmazonS3FullAccess

![[lambda_api_dashboard_iam_role.png]]

#### Lambda

Create a lambda function and insert the following code.

![[dashboard_api_function.png]]

```javascript
import {
  AthenaClient,
  StartQueryExecutionCommand,
  GetQueryExecutionCommand,
  GetQueryResultsCommand,
} from "@aws-sdk/client-athena";

const athena = new AthenaClient({});
const DATABASE = "classroom_analytics_db";
const S3_QUERY_RESULTS =
  "s3://utility-classroom-data-lake/athena-query-results/";

export const handler = async (event) => {
  try {
    const query = `SELECT "classId", "currentCount" FROM "classroom_analytics"."classroom_classroom" ORDER BY "currentCount" DESC LIMIT 10`;
    const params = {
      QueryString: query,
      QueryExecutionContext: { Database: DATABASE },
      ResultConfiguration: { OutputLocation: S3_QUERY_RESULTS },
    };

    const startQueryResult = await athena.send(
      new StartQueryExecutionCommand(params),
    );
    const queryExecutionId = startQueryResult.QueryExecutionId;

    // Poll for the query status until it completes
    let status = "QUEUED";
    while (status === "QUEUED" || status === "RUNNING") {
      const getStatusResult = await athena.send(
        new GetQueryExecutionCommand({ QueryExecutionId: queryExecutionId }),
      );
      status = getStatusResult.QueryExecution.Status.State;
      if (status === "FAILED" || status === "CANCELLED")
        throw new Error("Athena query failed or was cancelled.");
      if (status !== "SUCCEEDED")
        await new Promise((resolve) => setTimeout(resolve, 1000)); // Wait for 1 second before polling again
    }

    // Get and format the query results
    const results = await athena.send(
      new GetQueryResultsCommand({ QueryExecutionId: queryExecutionId }),
    );
    const formattedResults = results.ResultSet.Rows.slice(1).map((row) => {
      const data = row.Data;
      return {
        classId: data[0].VarCharValue,
        currentCount: parseInt(data[1].VarCharValue),
      };
    });

    return {
      statusCode: 200,
      headers: {
        "Content-Type": "application/json",
        "Access-Control-Allow-Origin": "*",
      },
      body: JSON.stringify(formattedResults),
    };
  } catch (error) {
    console.error("Error running Athena query:", error);
    return {
      statusCode: 500,
      headers: {
        "Content-Type": "application/json",
      },
      body: JSON.stringify({
        message: "Internal server error",
      }),
    };
  }
};
```

# Dashboard

## API Gateway

Navigate to the API Gateway console and create an API

![[api_gateway_front_page.png]]

Select REST API

![[rest_api_create.png]]

Give the API a name and a description

![[create_rest_api.png]]

Navigate to the created API and press create resource

![[create_resource.png]]

Name the resource and create resource

![[provide_resource_details.png]]

Create a method

![[create_method_api.png]]

Select GET method type and choose the lambda function that queries the data with AWS Athena

![[create_method_config.png]]

Deploy the API

![[deploying_api.png]]

Copy the invoke URL from the Stages section

![[api_gateway_stages.png]]

Append the created resource name

`https://sugbccz646.execute-api.ap-southeast-1.amazonaws.com/test/<resource>`

## Dashboard

Create a bucket to host the static website

![[dashboard_bucket.png]]

Enable s3 static website hosting

![[enable_static_website_hosting.png]]

Upload the dashboard HTML code

![[bucket_dashboard.png]]

View the dashboard with the object link provided

![[index_dashboard.png]]

![[live_classroom_dashboard.png]]

