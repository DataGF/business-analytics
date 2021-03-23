# LOGISTIC REGRESSION

*Rundown: Logistic Regression is a measurable technique used to anticipate binary results by investigating the result's relationship with at least one predictor factors.*

## SATEGE 1: SELECT TARGET AND PREDICTOR VARIABLES 
Target Variable: the target variable is the variable we are attempting to anticipate with the model. This ought to be a binary variable: “yes” or “no”, “true” or “false”, 0 or 1, and so on. Predictor variables: they are utilized to help anticipate the target variable. Predictor variables ought to be: relevant to the target variable, not exceptionally correlated to other predictor factors, and don't have a high number of missing qualities. Good tool for Alteryx users: Association Analysis.

## SATEGE 2: PREPARE DATA 
Setting up the information incorporates managing issues like missing, dirty, or duplicate information; eliminating anomalies; mixing and arranging information, and so on. Your last dataset ought to incorporate one line for every result furthermore, set of predictor variables. Assessment and approval tests: next, split the informational index into two sections: one section for estimation (for preparing the model) and one section for validation (to assist us with checking that we are making a helpful model). Good tool for Alteryx users: Create Samples.

## SATEGE 3: BUILD AND RUN THE MODEL 
Run the model with the target and predictor variables. Notice the factual meaning of every one of the indicator factors by taking a gander at the p-value in the yield. Assuming it's underneath 0.05, the connection between the target and predictor variable is genuinely huge. If not, it isn't critical and can be prohibited from the model. R-squared is a gauge somewhere in the range of 0 and 1 of the logical force of them model, and can be utilized to think about models and select the best one. Utilizing a method called "stepwise relapse" can consequently distinguish the best mix of indicator factors. Valuable Alteryx instruments: Linear Regression, Stepwise.

## SATEGE 4: MODEL VALIDATION 
Apply the model to the approval test and see how precisely the model predicts the results. This progression dodges overfitting and encourages you see how precise your expectations will be on new information. Good tool for Alteryx users: Model Comparison. 

## SATEGE 5: APPLY THE MODEL TO MAKE PREDICTIONS 
Apply the model to another dataset to make forecasts. This dataset ought to have all the indicator variable values, which are gone through the model to anticipate the obscure objective variable worth. The forecast will be a number somewhere in the range of 0 and 1, addressing the probability of positive result. Good tool for Alteryx users: Score.

## CASE STUDY

Based on the data of a fictional hotel (hotelloyaltydata.csv), your boss asks you the following:

- Create a dataset that contains only the individuals who have a greater than 50% probability of redeeming an offer.
- Only include the Customer Key, First and Last Names, and the likelihood they will redeem an offer.
- Sort the data with the highest likelihood individuals are at the top.

1. Stage One: deselect Customer Key, First Name, Last Name, and Redeemer as predictor variables. Motivation: Customer Key, First Name and Last Name there is no correlation on predicting a customer behavior and Redeemer is our target variable.
2. Stage Two: deselect any categorical, non-numeric variables that contain more than four categories. Motivation: keep our model simple and effective. In addition, we adjust several the data types, like: "Spend" from string to double, "Stays Per Year" from string to double, "Total Days Stayed" from string to double and "Years Of Loyalty" from string to double.
3. Stage Three: there was built and ran two models, a decision tree and a logistic regression for this issue.
4. Stage Four: the two models that were built on the previous stage were compared and we choose logistic regression for our prediction.
5. Stage Five: customer behavior was predict when the model was applyed on our data.
