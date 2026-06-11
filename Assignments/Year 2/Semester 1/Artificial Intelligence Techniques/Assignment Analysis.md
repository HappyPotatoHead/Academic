# Objective 
Train a machine learning model that can accurately predict the cardiovascular risk using information provided in the dataset.  

*Labels:*
1. Low
2. Medium
3. High
```python
cardio_df:pd.DataFrame = pd.read_csv('dataset.csv')
cardio_df.head()
```
Based on the dataset, this is a supervised, offline classification problem.

## Background
Cardiovascular diseases are one of the most significant health challenges worldwide, contributing to millions of death each year. Early detection and accurate prediction of cardiovascular risk in an individual can save that individual from costs of treatment, pain, and stress, leading to an overall healthier and happier life. However, while there are ways to predict a person's cardiovascular risk - low, medium, high - it is difficult to do so accurately risk due to the wide array of complex and multifaceted factors - demographic, lifestyle habits, and pre-existing conditions - involved and the dissimilarities amongst us. With the rise of machine learning and AI, diagnosis of cardiovascular risk has been made easier and smoother, albeit the predictions still require professionals' insights. Nonetheless, machine learning offers a powerful set of tools capable of analysing large datasets and uncover patterns that may not be evident under statistical methods; machine learning can help doctors and researchers to learn and uncover unsuspected correlations and new trends, allowing them to make informed decisions.

To solve this issue, machine learning techniques are used to analyse a dataset that includes features such as gender, age, family history, and more. By employing multiple models, we can determine which model does the best in predicting cardiovascular risks in individuals under specific conditions, showing us the most significant factor while uncovering patterns and previously unknown correlations within the data. This process involves selecting and training models followed by fine tuning them. The ultimate goal is to narrow down the models that is both robust and reliable in assisting healthcare professionals and researchers in identifying at-risk individuals, thereby facilitating timely medical interventions. 

## Objectives
The objectives of the project are to find out the relevant factors that contribute to cardiovascular risk of an individual, develop and optimise machine learning models that can accurately predict the cardiovascular risk level of an individual. This is achieved through data exploration and pre-processing, model selection and training, model tuning and evaluation, and result analysis and interpretation. In data exploration and pre-processing, the dataset is visualised and processed to handle missing values, outliers, and noise, to ensure only cleaned relevant data is used for model training. Furthermore, in model selection and training, various models are chosen and trained to determine the most effective mode. The selected models are then fine-tuned and analysed once more.

## Performance Measure
1. Confusion Matrix
	1. Accuracy
	2. Precision 
		2. When False Positive is of higher concern than False Negative
	3. Recall
		1. When False Negative is of higher concern than False Positive
	4. $F_1 \text{ score}$
		1. When FP and and FN equally costly
		2. Adding more data doesn't effectively change the outcome
		3. True Negative is High
4. AUC-ROC
	1. ROC is a probability curve that plots the TPR against the FPR at various threshold values and separates the *signal* from the *noise*.
		1. AUC is essentially the area under the curve. 
			1. The greater the value of AUC, the better the model will perform. 
				1. If the AUC is 1, the model is perfectly able to distinguish between positives and negatives
				2. If the AUC is 0, the model will predict all Negatives and Positives
				3. If the AUC is 0.5, the model is unable to distinguish between negatives and positives.
# Getting the Data
We now have to split the *original* dataset into *training* and *test* set. 

```python
from sklearn.model_selection import train_test_split
X_cardio_df:pd.DataFrame = cardio_df.iloc[:, :-1]
y_cardio_df:pd.Series= cardio_df.iloc[:, -1]

# strafity = y_cardio_df is to make sure both training set and test set have the same distribution of label
X_train, X_test, y_train, y_test = train_test_split(X_cardio_df, y_cardio_df, test_size=0.2, random_state= 42, stratify=  y_cardio_df)
```

Leave the test set untouched. And move on to the next step

>[!WARNING] Test set
>Leave the test set unbothered and focus purely on the training set to prevent data leakage

# Data Analysis
Create a copy of the original data for exploration.
## Feature Studying
The dataset has 17 features, 1 label and 2100 rows:
```python 
row, column = cardio_df.shape
print(f"The number of rows: {row}\nThe number of columns: {column}\n")

cardio_df.info()
```
```
RangeIndex: 2100 entries, 0 to 2099
Data columns (total 18 columns):
 #   Column                  Non-Null Count  Dtype  
---  ------                  --------------  -----  
 0   Gender                  2100 non-null   object 
 1   Age                     2100 non-null   int64  
 2   Height(cm)              2100 non-null   float64
 3   Weight(kg)              2100 non-null   float64
 4   Family_history          2100 non-null   object 
 5   Alcohol                 2100 non-null   object 
 6   Junk_food               2100 non-null   object 
 7   Vege_day                2100 non-null   int64  
 8   Meals_day               2100 non-null   int64  
 9   Snack                   2100 non-null   object 
 10  Smoking                 2100 non-null   object 
 11  Water_intake(L)         2100 non-null   float64
 12  Transportation          2100 non-null   object 
 13  Exercise                2100 non-null   int64  
 14  TV                      2100 non-null   object 
 15  Income                  2100 non-null   int64  
 16  Discipline              2100 non-null   object 
 17  Cardiovascular_risk(y)  2100 non-null   object 
dtypes: float64(3), int64(5), object(10)
memory usage: 295.4+ KB
```
We can obtain some information from the output above:
1. There are 17 features
2. There is no `null` values
2. Most of the data in the dataset are of `string` type.
3. The memory usage is 295.4+ KB

```python
# This lists out the columns
feature_list:list[str] = list(cardio_df.columns)
```

| **No** | Feature        | **Unit** | **Datatype** | **Input**                           | **Conversion**                     | Skewness                       |
| ------ | -------------- | -------- | ------------ | ----------------------------------- | ---------------------------------- | ------------------------------ |
| 1      | Gender         | -        | String       | Female,Male                         | Single characters/One Hot Encoding | Bell                           |
| 2      | Age            | -        | Int          | 17                                  | -                                  | Right                          |
| 3      | Height         | cm       | Float        | 172.2                               | -                                  | Bell                           |
| 4      | Weight         | kg       | Float        | 70                                  | -                                  | Slightly Right                 |
| 5      | Family history | -        | String       | no, yes                             | Binary                             |                                |
| 6      | Alcohol        | -        | String       | none, low, medium, high             | Label Encoding                     |                                |
| 7      | Junk food      | -        | String       | yes, no                             | Binary                             |                                |
| 8      | Vege day       | -        | Int          | 1,2,3                               | -                                  |                                |
| 9      | Meals day      | -        | Int          | 1, 2, 3, 4                          | -                                  |                                |
| 10     | Snack          | -        | String       | sometimes, frequently, always, no   | Label Encoding                     | *Sometimes* dominates the data |
| 11     | Smoking        | -        | String       | yes no                              | One Hot Encoding                   |                                |
| 12     | Water Intake   | L        | Float        | -                                   | -                                  |                                |
| 13     | Transportation | -        | String       | walk, bicycle, motorcycle, car, bus | One Hot Encoding                   |                                |
| 14     | Exercise       | -        | Int          | 0,1,2,3                             | -                                  |                                |
| 15     | TV             | -        | String       | rare, moderate, often               | Label Encoding                     |                                |
| 16     | Income         | -        | Int          | -                                   | -                                  |                                |
| 17     | Discipline     | -        | String       | -                                   | -                                  |                                |

## Visualising the Data
### Numerical Data

```python
cardio_df_copy.hist(bins = math.ceil(2 * math.sqrt(row)), figsize=(20,15))
plt.show()
```

![[histogram.png]]
Since the number of rows is 2k so, a good formula to get the bins is *Rice Rule*
$$
k = \lceil 2 * \sqrt{n} \rceil
$$
According to the histograms,
1. The age is skewed to the right
2. Most people are about 170cm
3. Most people are >75kg
4. The income is not scaled properly
5. There exists outliers in height and weight

### Categorical Data
![[categorical-data.png]]
**Text Format**
What we know:
1. The gender demographic is balanced
2. A lot of values dominate each other
	1. This will result in biased outcome in certain model
		1. K-NN
		2. Logistic Regression

*So, how do we deal with the unbalanced categorical data?*

1. `class_weight= 'balanced`
	1. A lot of models in `sklearn` have this parameter

## Target Attributes
1. Gender
	1. Both genders are properly represented
2. Age
	1. Data is skewed
3. BMI
	1. $BMI = \frac{weight(kg)}{height(cm)^2}$
4. Family history
	1. *yes* dominates
5. Alcohol
	1. *low*d dominates
6. Junk food
	1. 
7. Smoking
8. Exercise
9. Discipline
# Pre-processing
Height and weight alone do not carry much value and does not necessarily correlate to cardiovascular risk. So, they are better combined and turned into BMI. Age is also heavily skewed, so discretising them would benefit as well. 
```python
def newFeatures(dataframe:pd.DataFrame)->bool:
    dataframe['BMI'] = (dataframe['Weight(kg)']/ np.square(dataframe['Height(cm)']/100)).apply(lambda x:round(x,2))
    dataframe['age_cat'] = pd.cut(dataframe['Age'], bins = [13,20,30,40,dataframe['Age'].max()], labels=[1,2,3,4])
    return True
```
![[age-cut.png]]
# Machine Learning

^3c7830
## Shortlisting Models
### K-NN
>[!DEFINITION]
>K-Nearest Neighbors (KNN) is a simple, instance-based machine learning algorithm used for classification and regression.
#### Classification
1. **Choose the Number of Neighbours (K)**
	1. Number of nearest neighbours to consider. 
	2. This is a hyperparameter
2. **Calculate Distances** 
	1. Compute the distance between a point and all other points in the training dataset. 
	2. Common distance metrics include,
		1. Euclidean distance
		2. Manhattan distance
		3. Minkowski distance.
3. **Find Nearest Neighbors**
	1. Identify the K data points in the training set that are closest to the query point based on the distance calculations.
4. **Vote for Classification** 
	1. Count the number of occurrences of each class among the K nearest neighbors. 
		1. The class with the majority vote is assigned to the query point.
5. **Assign the Class** 
	1. Assign the class label to the query point based on the majority vote from the nearest neighbours.
#### Initial Training
Training is done with `StratifiedKFold`. This gives me more manual control over what metrics is calculated. The initial model is done with default hyperparameter. 
```python
from sklearn.model_selection import StratifiedKFold
from sklearn.neighbors import KNeighborsClassifier
from sklearn.metrics import accuracy_score, precision_score, recall_score, f1_score

skf = StratifiedKFold(n_splits=5, shuffle=True, random_state=42)
cv_accuracy=[]
cv_f1_score=[]

for train_index, val_index in skf.split(X_train_processed, y_train_processed):
	X_train_fold, X_val_fold = X_train_processed[train_index], X_train_processed[val_index]
	y_train_fold, y_val_fold = y_train_processed[train_index], y_train_processed[val_index]
	
	knn_model:KNeighborsClassifier = KNeighborsClassifier()
	knn_model.fit(X_train_fold, y_train_fold)
	
	y_pred = knn_model.predict(X_val_fold)
	
	accuracy = accuracy_score(y_val_fold, y_pred)
	f1 = f1_score(y_val_fold, y_pred,average='weighted')
	
	cv_accuracy.append(accuracy)
	cv_f1_score.append(f1)

print(f'Cross-Validation Accuracy Scores: {cv_accuracy}')
print(f'Average Accuracy: {sum(cv_accuracy) / len(cv_accuracy)}')
print(f'Cross-Validation F1 Scores: {list(map(float, cv_f1_score))}')

print(f'Average F1: {sum(cv_f1_score) / len(cv_f1_score)}')
```
**Output**
```
Cross-Validation Accuracy Scores: [0.9821428571428571, 0.9910714285714286, 0.9910714285714286, 0.9940476190476191, 0.9910714285714286]
Average Accuracy: 0.9898809523809524
Cross-Validation F1 Scores: [0.9821984288315017, 0.9911044119398275, 0.9910665175160974, 0.9940280119111374, 0.99106138818397]
Average F1: 0.9898917516765067
```
The model is trained once again on the entire training set
```python
final_knn_model = KNeighborsClassifier()
final_knn_model.fit(X_train_processed, y_train_processed)
```
##### Result analysis
Surprisingly the model does extremely well on the training set. 

>[!WARNING] Overfitting
>The model may be overfitting

*So, how do we know if it is actually overfitting?*
We test it. 
#### Testing Model
We pre-process the model the same way with the same functions
```python
newFeatures(X_test)

X_test_processed = processing(X_test, one_encoder, ordinal_encoder)
y_test_processed = y_preprocessing(pd.DataFrame(y_test), y_ordinal_encoder)

y_test_pred = final_knn_model.predict(X_test_processed)
test_accuracy = accuracy_score(y_test_processed, y_test_pred)

print(f'Test Set Accuracy: {test_accuracy}')
```
**Output**
```
Test Set Accuracy: 0.9857142857142858
```

It still does well...?

**Confusion Matrix**
```python
import numpy as np
import seaborn as sns
from sklearn.metrics import confusion_matrix

cm = confusion_matrix(y_test_processed, y_test_pred, labels=[0.0, 1.0, 2.0])
plt.figure(figsize=(8, 6))

sns.heatmap(cm, annot=True, fmt='d', cmap='Blues', xticklabels=['Low', 'Medium', 'High'], yticklabels=['Low', 'Medium', 'High'])

plt.xlabel('Predicted Label')
plt.ylabel('True Label')
plt.title('Confusion Matrix')
plt.show()
```
![[confusion-matrix-knn.png]]
**Learning Curves**
```python
from sklearn.model_selection import learning_curve

train_sizes, train_scores, val_scores = learning_curve(final_knn_model, X_train_processed, y_train_processed, cv=5, scoring='accuracy')

train_scores_mean = train_scores.mean(axis=1)
train_scores_std = train_scores.std(axis=1)
val_scores_mean = val_scores.mean(axis=1)
val_scores_std = val_scores.std(axis=1)

plt.figure()
plt.plot(train_sizes, train_scores_mean, 'o-', color='r', label='Training score')
plt.plot(train_sizes, val_scores_mean, 'o-', color='g', label='Validation score')
plt.fill_between(train_sizes, train_scores_mean - train_scores_std, train_scores_mean + train_scores_std, alpha=0.1, color='r')
plt.fill_between(train_sizes, val_scores_mean - val_scores_std, val_scores_mean + val_scores_std, alpha=0.1, color='g')
plt.xlabel('Training examples')
plt.ylabel('Score')
plt.legend(loc='best')
plt.title('Learning Curves')
```
![[learning-curves-knn.png]]

Visualisation shows that the model works really well. Regardless, there is always room for improvement
##### Hyperparameter
The hyperparameter to focus on:
1. `n_neighbour`
2. distance `metric`
```python
from sklearn.model_selection import GridSearchCV

param_grid = {
    'n_neighbors': range(1,21),
    'metric':['euclidean', 'manhattan', 'minkowski']
}

knn_testing = KNeighborsClassifier()
grid_search = GridSearchCV(estimator=knn_testing, param_grid=param_grid, cv=5, scoring='accuracy')
grid_search.fit(X_train_processed, y_train_processed)

best_knn = grid_search.best_estimator_
test_score = best_knn.score(X_test_processed, y_test_processed)
print(f'Test set score: {test_score}')
```
**Output**
```
Test set score: 0.9880952380952381
```
The best parameter is `euclidean` and `8` with test score of `0.988`.

The new confusion matrix
![[best-knn-matrix.png]]

### RandomForestClassifier
>[!DEFINITION]
>The RandomForestClassifier is an ensemble learning method used for classification tasks. It builds on the concept of decision trees and improves their performance through a technique known as "bagging"

>[!WARNING] TBD
>To be filled

>[!WARNING] Outcome
>May result in **Low training error but high test error**
### Logistic Regression
>[!DEFINITION]
>Logistic Regression is a fundamental classification algorithm used to predict binary outcomes (i.e., outcomes with two possible classes).

>[!WARNING] TBD
>Incomplete

>[!WARNING] Before execution
>Research on how to extend to OvR

## K-Fold Training

Since the dataset is relatively small - $2,000$ - rows of data **only**, K-fold training can be done with `StratifiedKFold`. 

```python
from sklearn.model_selection import train_test_split
X_cardio_df:pd.DataFrame = cardio_df.iloc[:, :-1]
y_cardio_df:pd.Series= cardio_df.iloc[:, -1]

X_train, X_test, y_train, y_test = train_test_split(X_cardio_df, y_cardio_df, test_size=0.2, random_state= 42, stratify=  y_cardio_df)
```

>[!WARNING] 
>However, this is used on the training set to validate our model. 

## Fine Tuning
Use Grid Search

>[!WARNING] TBD
>KNN is done



![[Pasted image 20240906095236.png]]