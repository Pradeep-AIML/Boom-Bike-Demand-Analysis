# Boom Bikes Demand Analysis
> **Problem Statement**
A bike-sharing system is a service in which bikes are made available for shared use to individuals on a short term basis for a price or free. Many bike share systems allow people to borrow a bike from a "dock" which is usually computer-controlled wherein the user enters the payment information, and the system unlocks it. This bike can then be returned to another dock belonging to the same system.


A US bike-sharing provider **BoomBikes** has recently suffered considerable dips in their revenues due to the ongoing Corona pandemic. The company is finding it very difficult to sustain in the current market scenario. So, it has decided to come up with a mindful business plan to be able to accelerate its revenue as soon as the ongoing lockdown comes to an end, and the economy restores to a healthy state. 


In such an attempt, BoomBikes aspires to understand the demand for shared bikes among the people after this ongoing quarantine situation ends across the nation due to Covid-19. They have planned this to prepare themselves to cater to the people's needs once the situation gets better all around and stand out from other service providers and make huge profits.


They have contracted a consulting company to understand the factors on which the demand for these shared bikes depends. Specifically, they want to understand the factors affecting the demand for these shared bikes in the American market. The company wants to know:

- Which variables are significant in predicting the demand for shared bikes.
- How well those variables describe the bike demands

Based on various meteorological surveys and people's styles, the service provider firm has gathered a large dataset on daily bike demands across the American market based on some factors.  

**Business Goal:**

You are required to model the demand for shared bikes with the available independent variables. It will be used by the management to understand how exactly the demands vary with different features. They can accordingly manipulate the business strategy to meet the demand levels and meet the customer's expectations. Further, the model will be a good way for management to understand the demand dynamics of a new market.

**Data Preparation:**

1. You can observe in the dataset that some of the variables like 'weathersit' and 'season' have values as 1, 2, 3, 4 which have specific labels associated with them (as can be seen in the data dictionary). These numeric values associated with the labels may indicate that there is some order to them - which is actually not the case (Check the data dictionary and think why). So, it is advisable to convert such feature values into categorical string values before proceeding with model building. Please refer the data dictionary to get a better understanding of all the independent variables.
 
1. You might notice the column 'yr' with two values 0 and 1 indicating the years 2018 and 2019 respectively. At the first instinct, you might think it is a good idea to drop this column as it only has two values so it might not be a value-add to the model. But in reality, since these bike-sharing systems are slowly gaining popularity, the demand for these bikes is increasing every year proving that the column 'yr' might be a good variable for prediction. So think twice before dropping it. 

**Model Building**

In the dataset provided, you will notice that there are three columns named 'casual', 'registered', and 'cnt'. The variable 'casual' indicates the number casual users who have made a rental. The variable 'registered' on the other hand shows the total number of registered users who have made a booking on a given day. Finally, the 'cnt' variable indicates the total number of bike rentals, including both casual and registered. The model should be built taking this 'cnt' as the target variable.

```
from sklearn.metrics import r2_score
r2_score(y_test, y_pred)
```
- where y_test is the test data set for the target variable, and y_pred is the variable containing the predicted values of the target variable on the test set.
- Please don't forget to perform this step as the R-squared score on the test set holds some marks. The variable names inside the 'r2_score' function can be different based on the variable names you have chosen.


**Model Evaluation:**

When you're done with model building and residual analysis and have made predictions on the test set, just make sure you use the following two lines of code to calculate the R-squared score on the test set.

## Table of Contents
* [General Info](#general-information)
* [Technologies Used](#technologies-used)
* [Conclusions](#conclusions)
* [Acknowledgements](#acknowledgements)

<!-- You can include any other section that is pertinent to your problem -->

## General Information
- From your analysis of the categorical variables from the dataset, what could you infer about their effect on the dependent variable? 


# Assignment-based Subjective Questions
1. From your analysis of the categorical variables from the dataset, what could you infer about their effect on the dependent variable? (3 marks)

    **Ans:** - 'season','weathersit','mnth'

1. Why is it important to use drop_first=True during dummy variable creation? (2 mark)

   **Ans:** - Using drop_first=True during dummy variable creation is important for several reasons related to multicollinearity and the interpretation of regression models.

1. Looking at the pair-plot among the numerical variables, which one has the highest correlation
with the target variable? (1 mark)

   **Ans:** - highest correlation temp and adjusted Temp  , and rentals, followed by the two adjacent months, which seems to be corelated with seasonal trends.
   
   To validate the assumptions of Linear Regression after building the model on the training set, you typically check the following key assumptions:

   Linearity
   Scatter Plot
   Independence
   Plot of Residuals vs. Fitted Values

1. How did you validate the assumptions of Linear Regression after building the model on the
training set? (3 marks)
   
   **Ans:** After building the Linear Regression model on the training set, the assumptions are typically validated through a combination of visual inspections and statistical tests.
   
1. Based on the final model, which are the top 3 features contributing significantly towards
explaining the demand of the shared bikes? (2 marks)
 
   **Ans:** To identify the top 3 features contributing significantly towards explaining the demand for shared bikes in a Linear Regression model, follow these steps:

   - Fit the Model:
   - Check Feature Coefficients -After fitting the model, you can extract and review the coefficients of the features. Features with larger absolute coefficients generally have a more significant impact on the model's predictions.
   - Statistical Significance.
   - Check the p-values associated with each feature to determine statistical significance. - 
   - Features with low p-values (typically less than 0.05) are considered significant.

# General Subjective Questions
1. Explain the linear regression algorithm in detail. (4 marks)
  
   **Ans:** Linear regression models the relationship between dependent and independent variables by fitting a linear equation to observed data, minimizing the difference between predicted and actual values. 
2. Explain the Anscombe’s quartet in detail. (3 marks)

   **Ans:** Anscombe’s quartet is a set of four datasets with identical summary statistics but differing distributions, highlighting the importance of visualizing data beyond summary statistics.

3. What is Pearson’s R? (3 marks)

   **Ans:** Pearson’s R, or Pearson correlation coefficient, measures the linear relationship between two variables. It ranges from -1 to 1, where -1 indicates a perfect negative correlation, 1 indicates a perfect positive correlation, and 0 indicates no linear correlation.

4. What is scaling? Why is scaling performed? What is the difference between normalized scaling
and standardized scaling? (3 marks)

   **Ans:** Scaling adjusts data range or distribution. Normalized scaling adjusts to a [0, 1] range, while standardized scaling centers data with zero mean and unit variance.

5. You might have observed that sometimes the value of VIF is infinite. Why does this happen?
(3 marks)

   **Ans:** Infinite VIF occurs when predictor variables are perfectly collinear, leading to an undefined or infinitely large variance in the regression coefficient estimates.

6. What is a Q-Q plot? Explain the use and importance of a Q-Q plot in linear regression.
(3 marks)

   **Ans:** A Q-Q plot compares data distribution to a theoretical distribution. In linear regression, it checks residual normality, ensuring model validity and reliable hypothesis testing.
<!-- You don't have to answer all the questions - just the ones relevant to your project. -->



This looks a regression problem and can be solved using Linear Regression Analysis. 
