# Faculty Activity Monitoring & Space Utilisation Analytics

# How this would work.

There would be sensors placed all over the faculty to keep track of the distribution and density of occupants in the faculty; this includes classrooms, restrooms, and general areas.

The feedback from the sensors would be passed to the system and visualised with a heatmap. For each room, LIDAR sensors to count people going in and out of the room.

If the number of people in any classroom is 0 for a period of time, the lights and air-conditioner in the room would be switched off. The same is applied to meeting rooms and other non-personal accessible areas.

Create alerts on broken facilities or overflowed facilities.

# How This would Benefit The University / Objective

1. Optimise space utilisation
   - Some areas being overcrowded while others remain consistently empty
   - By providing real-time and historical data on occupancy, activity levels, and peak usage times, the system allows faculty administration to identify underutilized classrooms, labs, offices, and study areas. This data can then inform decisions on re-purposing spaces, optimizing timetabling, or justifying investment in new facilities.
   - Renovate certain areas and classrooms
2. Real-time adjustment of facilities
   - For example, turning off the air-conditioner, lights, or fans when no one is using classrooms or meeting rooms.
3. Data-driven resource management and planning
   - The faculty is able to make better informed decision on which facility to invest.
   - Can manage their finances much better
   - For instance, cleaning schedules can be optimized based on actual traffic, IT resources can be deployed to high-usage areas, and future campus development can be tailored to demonstrated needs.

# How this can be implemented with AWS

Services:

1. AWS IoT Core
   - For the sensors and cameras
2. Amazon Kinesis
   - Collect, process, and analyse real-time video and data streams
3. AWS Lambda
4. AWS DynamoDB
   - Fast, scalable NoSQL database
5. AWS IoT Events
   - Detecting and responding to events from IoT sensors
6. Amazon SNS
   - To send real-time alerts or notifications
7. Amazon S3
   - Data lake
8. AWS Glue
   - Clean, transform, and aggregate raw sensor data
9. AWS Athena
   - Run standard SQL queries
10. Amazon QuickSight
