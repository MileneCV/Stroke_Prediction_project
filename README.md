# Stroke Prediction 
#### Author: Milene Carmes Vallejo


![dataset-cover (2)](https://user-images.githubusercontent.com/112773242/203482910-40b46c69-0c62-4bee-802e-4a0d89acdca2.jpg)




### Data:

According to the World Health Organization (WHO), stroke is the second leading cause of death globally, responsible for approximately 11% of total deaths. This dataset is used to predict whether a patient is likely to get a stroke based on the input parameters like gender, age, various diseases, and smoking status. Each row in the data provides relevant information about the patient.

### Methods

#### Exploratory Visual and Analysis: 

- The original dataframe was divided into 2: patients who had stroke and patients who didn't. 
- Boxplot, barplot, lineplot and histplot were created to find a correlation between stroke and other features. 

#### Machine Learning part: 
- Dropping unnecessary columns.
- Data preparation: check duplicates, check inconsistencies values, check the type of all columns. 
- Train/Test split: "stroke" column as the target.
- Make selector columns because there are numbers and objects columns in this dataset.
- Check missing values: There are missing values in the numeric column BMI which is float number and was used SimpleImputer with ‘mean strategy'.
- I used OHE for categorical columns and scaler for numeric columns since in machine learning the dataset needs to be all numeric and in the same scale. 
- I made a numeric_pipe with scaler and SimpleImputer. 
- I used make_column_transform to put all together (numeric and categorical). 
- The stroke column is unbalanced so I will use SMOTE to oversample my data.
- I used 4 Models:  logistic regression, Decision Tree Classifier, Randon Forest, and XGBClassifier. 
- I tunned and/or used PCA and some features engineering. 
- Evaluated the performance with classification_report and ConfusionMatrixDisplay.
- I was looking for a model with a lower false negative rate which means with higher recall. 
 

### Results

![Stroke_Prediction_project_2](stroke12.png)

Patients who had a stroke (1) are older than 40 years old and have higher glucose levels than patients who didn't have a stroke (0). 


![Stroke_Prediction_project_2](heart.png)

Patients who had stroke about 20% have heart disease and patients who didn’t have stroke less than 5% have heart disease. 



![Stroke_Prediction_project_2](hypertension.png)

Patients who had stroke about 25% have hypertension and patients who  didn’t have stroke less than 10 % have hypertension. 



### Model
The best model tested was Logistic Regression after we change the original dataframe with some feature engineering. 

#### The most important metrics

Since this prediction is to diagnose stroke the better model is one with a lower False negative rate and better recall. With logistic regression in the test data, the accuracy was 75%, recall 82% and the false negative rate was 17%.  Was the better model: 

![Stroke_Prediction_project_2](stroke4.png)


### Recommendations:
Patients older than 40 years old, with high glucose levels or/and hypertension or/and heart disease have higher risk to have a stroke. So is better to monitor for stroke symptoms and seek help in case of any symptom.

  

### Limitations & Next Steps
The best model has 17% of false negative rate and 75% of accuracy. The prediction is not perfect, maybe due to the dataset being unbalanced as 95% of patients didn't have a stroke and only 5% had.

### For further information
For any additional questions, please contact milene.c.vallejo@gmail.com
