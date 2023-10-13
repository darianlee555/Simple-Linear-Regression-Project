# Simple Linear Regression Project 

## Context

As part of my coursework at Stony Brook University, I was required to perform data analysis involving simple linear regression models. Here is one such project that demonstrates me making a simple linear regression model based on data sets and analyzing the model. This project is broken into two parts (A and B), both with different objectives. Please take a look below!

## Part A

### Part A Objective

The objective of Part A was to analyze two data sets, one with Independent Variable (IV) values and one with Dependent Variable (DV) values (both with 438 observations sorted by ID) and make a simple linear regression model based off these data sets and analyze the model. I had to merge the two data sets (pairing IV and DV values together by their associated ID) and had to check and account for any missing IV or DV values and then make an estimated linear regression model. I had to test if x has any value in predicting y and then make a confidence interval (CI) for the true slope and true intercept of the model. The background/purpose of this project is to be able to merge data sets, account for missing data, make an estimated simple linear regression model once the missing data is accounted for, and then analyze said model’s accuracy.

### Part A Data Sources

**Project 1 Part A IV Values**: https://github.com/darianlee555/Simple-Linear-Regression-Project/blob/main/Project1_IV_Values.csv

**Project 1 Part A DV Values**: https://github.com/darianlee555/Simple-Linear-Regression-Project/blob/main/Project1_DV_Values.csv

### Methods For Part A
**ALL CODE USED CAN BE FOUND IN THE R CODE APPENDIX SECTION BELOW**

Using R, I merged the two data sets of IV and DV values together using R’s merge() function, sorting by the ID of the observations. I then checked for missing values with R’s any() and md.pattern() functions. 3 observations with both missing IV and DV values were then dropped because they add nothing of value and then the bootstrap method was used to approximate either a missing IV or DV value for observations that had only one of these values missing (in which 29 observations were missing only an IV value and 27 observations were missing only a DV value), resulting in a complete data set of 435 observations. An estimated linear model using the complete data was then made using the lm() function and the summary() function was used to analyze the linear model. I found the least-squares slope and intercept estimates and the coefficient of determination, r<sup>2</sup> using the summary() function. The kable() function along with the anova() function was also used to get a ANOVA table for the linear model. The confint() function at level .99 was used to find the range of likely values for the true slope and true intercept of the model.

### Results For Part A
**ALL CODE USED TO OBTAIN THESE RESULTS CAN BE FOUND IN THE R CODE APPENDIX SECTION BELOW**


The coefficient of determination, r<sup>2</sup> is .4989. The estimated linear regression model was found to be ŷ = 51.274 +  7.534x. The ANOVA table associated with this model is shown in the appendix. The F-value associated with Regression(x) is 433.0677 with df<sub>1</sub> = 1 and df<sub>2</sub> = 433, (extremely large!), with p-value = 0, (extremely small!), so clearly reject the null hypothesis that the slope of the model is zero. The 99% CI for true intercept is (36.958690, 65.588714) and the 99% CI for true slope is (6.597054, 8.470298).

### Conclusions and Discussion For Part A
I rejected that the slope of the model is zero, so x has some value in predicting y. The coefficient of determination, r<sup>2</sup>, of the model was .4989 so 49.89% of the variation of y can be explained by the changes in x indicating a rather strong positive association between x and y and the scatterplot of the data supports this. The other 50.11% of the variation of the dependent variable is presumedly due to random variability or unidentified variables. The estimated linear regression model was ŷ = 51.274 +  7.534x. The residual plot of the data seems to support linearity and no significant lack of fit for the model. I conclude that the model, ŷ = 51.274 +  7.534x accurately describes the relationship between x and y. This is because the residuals of the data seem to show general random scatter with no clear pattern indicating linearity and no significant lack of fit. So based off the residual plot, I have to say that there is good support for ŷ = 51.274 +  7.534x being an accurate model for the relationship between x and y.

### R Code Appendix For Part A
You can find the code I used along with tables, plots, and other graphics here: [https://github.com/darianlee555/Simple-Linear-Regression-Project/blob/main/Project%201%20Part%20A.pdf](https://github.com/darianlee555/Simple-Linear-Regression-Project/blob/main/Code%20for%20Part%20A.pdf) 

## Part B

### Part B Objective

The objective of Part B was to analyze one data set with 657 observations of IV and DV values sorted by ID and make a simple linear regression model based off this data. I had to analyze whether a transformation of the data was needed to achieve linearity for such a regression model. After seeing if a transformation was needed, I made the appropriate linear regression model and analyzed if the model fits the data using a lack of fit test. I also had to see if x had any value in predicting y and then had to make a confidence interval for the true slope and true intercept of the model. The background/purpose of this assignment was to analyze if different transformations of data were needed to achieve linearity for a regression model, then analyze said model’s accuracy through a lack of fit test.

### Part B Data Source

**Part B Dataset**:

### Methods For Part B
**ALL CODE USED CAN BE FOUND IN THE R CODE APPENDIX SECTION BELOW**

Using R, I made a linear model using the lm() function and the untransformed data. After using the summary() function to analyze the linear model and comparing the results to that of many different transformations of the data, I did not believe that a transformation was needed as the data already fits around a straight line pattern relatively well. Any transformations either decreased the r<sup>2</sup> value or if there was an increase in r<sup>2</sup>, it was so minute (less than 1% difference) that the change was negligible, making me believe that no transformation is needed. The kable() function along with the anova() function was then used to get a ANOVA table for the linear model. The confint() function at level .99 was used to find the range of likely values for the trueslope and true-intercept of the model. The summary() function was used to get the least-squares estimates for slope and intercept for the model as well as the r<sup>2</sup> value of .5661. The pureErrorAnova() function was used to find the lack of fit F-value after the appropriate grouping and binning of data (specifically on the IV values) was done using the cut() and ave() functions.

### Results For Part B
**ALL CODE USED TO OBTAIN THESE RESULTS CAN BE FOUND IN THE R CODE APPENDIX SECTION BELOW**

The coefficient of determination r<sup>2</sup> is .5661. The F-value associated with Regression(x) is 833.7511 with df<sub>1</sub> = 1, df<sub>2</sub> = 655 with p-value = 0, so clearly reject that the slope of the model is 0. The estimated regression equation was found to be ŷ = 6.433531 + 0.201973x. The 99% C.I. for true slope is (0.1841255, 0.2198201) and the 99% C.I. for true intercept is (6.3765603, 6.4905017). The F-value associated with lack of fit was 0.6441. The ANOVA table associated with this model is in the code appendix.

### Conclusions and Discussion For Part B
We rejected that the slope of the model is zero, so x has some value in predicting y. The coefficient of determination r<sup>2</sup> was .5661 so 56.61% of the variation of y can be explained by the changes in x, indicating a rather strong positive association between x and y and the scatterplot of the data supports this. The other 43.36% of the variation of y is presumably due to random variability or unidentified variables. The F-value associated with lack of fit was .6441 (fairly close to 1) with d<sub>1</sub> = 11 and df<sub>2</sub> = 644 and p-value = .7913, which is very large, so do not reject the null hypothesis that the model is appropriate in the lack of fit test. Thus, I state that there is no significant lack of fit. The estimated linear regression model was ŷ = 6.433531 + 0.201973x. I conclude based off the lack of fit test result that the model, ŷ = 6.433531 + 0.201973x accurately describes the relationship between x and y and no transformation of data is needed to achieve linearity (the data is already pretty linear). This is supported by the residual plot of the data which seems to indicate linearity as the residuals seem to show general random scatter with no clear pattern (which also supports no significant lack of fit). 

### R Code Appendix For Part B
You can find the code I used along with tables, plots, and other graphics here: https://github.com/darianlee555/Simple-Linear-Regression-Project/blob/main/Code%20for%20Part%20B.pdf

