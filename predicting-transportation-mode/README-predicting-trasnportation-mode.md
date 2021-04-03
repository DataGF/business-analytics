# Predicting Transportation Mode

## Step 1 - Verifying Data

Here we will utilize know transportation data of a firm's employees. The data was arranged in a alteryx format file: employees-transportationdata.yxdb. The missing data was arranged in a csv format file: missingemployee.csv.

Fist of all we need to know how is our data so we used Alteryx Field Sumary Tool to do that. We verifyed the following data.

1. [Employees Age](https://github.com/DataGF/business-analytics/blob/main/predicting-transportation-mode/1_checkingDataAge.pdf).
2. [Employees Distance from Job (in miles)](https://github.com/DataGF/business-analytics/blob/main/predicting-transportation-mode/1_checkingDataDriveDistanceMiles.pdf).
3. [Employees ID](https://github.com/DataGF/business-analytics/blob/main/predicting-transportation-mode/1_checkingDataEmployeeID.pdf).
4. [Employees Gender](https://github.com/DataGF/business-analytics/blob/main/predicting-transportation-mode/1_checkingDataGender.pdf).
5. [Employees Known Transportation Data](https://github.com/DataGF/business-analytics/blob/main/predicting-transportation-mode/1_checkingDataKnowTransportationMode.pdf).
6. [Employees Marital Status](https://github.com/DataGF/business-analytics/blob/main/predicting-transportation-mode/1_checkingDataMaritalStatus.pdf).

## Step 2 - Creating Samples (training and testing with known data)

At the previous step we verifyed that the known data is good and know we can go to training and testing some models to make our predictions. For this we had split our known data in 70% of training data and 30% of testing data with a random seed of 1. We used Alteryx Create Sample Tool for this.

![70% training data and 30% testing data with a random seed 1](https://github.com/DataGF/business-analytics/blob/main/predicting-transportation-mode/2_creating_samples.JPG)

## Step 3 - Predicting Transportation Mode with Non-Binary Classification Models

We worked with three classification models: decision tree, random forest and boosted models. Then the models was compared, scored and interpreted for the purpose of this work i.e. predicte the employees transportations mode of a firm.

### Step 3.1 - Decision Tree Model

- Target variable: Mode (transportation mode).
- Predictor variables: Gender, Age, Marital Status and Drive Distance Miles.
![Target and Predictor variables](https://github.com/DataGF/business-analytics/blob/main/predicting-transportation-mode/3_1_Decision_Tree_Target_Predictor_Variables.JPG)
- [Click here](https://github.com/DataGF/business-analytics/blob/main/predicting-transportation-mode/3_1_decisionTreeContructed.pdf) to see the model construction report.
- [Click here](https://github.com/DataGF/business-analytics/blob/main/predicting-transportation-mode/3_1_decisionTreeComparison.pdf) to see the model comparison report.
- Alteryx Tools: Decision Tree and Model Comparison.

### Step 3.2 - Random Forest Model

- Target variable: Mode (transportation mode).
- Predictor variables: Gender, Age, Marital Status and Drive Distance Miles.
![Target and Predictor variables](https://github.com/DataGF/business-analytics/blob/main/predicting-transportation-mode/3_2_Random_Forest_Target_Predictor_Variables.JPG)
- [Click here](https://github.com/DataGF/business-analytics/blob/main/predicting-transportation-mode/3_2_randomForestContructed.pdf) to see the model construction report.
- [Click here](https://github.com/DataGF/business-analytics/blob/main/predicting-transportation-mode/3_2_randomForestComparison.pdf) to see the model comparison report.
- Alteryx Tools: Forest Model and Model Comparison.
- **Consideration about the number of trees:** the percentage error for different numbers of trees stabilyzes around 25 to 50 trees and we could utilize 50 tress for the purpuse of this prediction. But, since there were no processing time consumption trouble we go on with our 500 trees.
- The **most important predictor variable** acording to this model is **Drive Distance Miles**.

### Step 3.3 - Boosted Model

- Target variable: Mode (transportation mode).
- Predictor variables: Gender, Age, Marital Status and Drive Distance Miles.
![Target and Predictor variables](https://github.com/DataGF/business-analytics/blob/main/predicting-transportation-mode/3_3_Boosted_Model_Target_Predictor_Variables.JPG)
- [Click here](https://github.com/DataGF/business-analytics/blob/main/predicting-transportation-mode/3_3_boostedModelContructed.pdf) to see the model construction report.
- [Click here](https://github.com/DataGF/business-analytics/blob/main/predicting-transportation-mode/3_3_boostedModelComparison.pdf) to see the model comparison report.
- Alteryx Tools: Forest Model and Model Comparison.
- The **most important predictor variable** acording to this model is also **Drive Distance Miles**.
