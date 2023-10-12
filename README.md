# Simple Linear Regression Project (Broken into 2 parts A and B, both with different objectives)

## Part A

### Part A Objective

The objective of Part A was to analyze two data sets, one with Independent Variable (IV) values and one with Dependent Variable (DV) values (both with 438 observations sorted by ID) and make a simple linear regression model based off these data sets and analyze the model. I had to merge the two data sets (pairing IV and DV values together by their associated ID) and had to check and account for any missing IV or DV values and then make an estimated linear regression model. I had to test if x has any value in predicting y and then make a confidence interval (CI) for the true slope and true intercept of the model. The background/purpose of this project is to be able to merge data sets, account for missing data, make an estimated simple linear regression model once the missing data is accounted for, and then analyze said model’s accuracy.

### Methods For Part A
**ALL CODE USED CAN BE FOUND IN THE R CODE APPENDIX SECTION BELOW**

Using R, I merged the two data sets of IV and DV values together using R’s merge() function, sorting by the ID of the observations. I then checked for missing values with R’s any() and md.pattern() functions. 3 observations with both missing IV and DV values were then dropped because they add nothing of value and then the bootstrap method was used to approximate either a missing IV or DV value for observations that had only one of these values missing (in which 29 observations were missing only an IV value and 27 observations were missing only a DV value), resulting in a complete data set of 435 observations. An estimated linear model using the complete data was then made using the lm() function and the summary() function was used to analyze the linear model. I found the least-squares slope and intercept estimates and the coefficient of determination, r<sup>2</sup> using the summary() function. The kable() function along with the anova() function was also used to get a ANOVA table for the linear model. The confint() function at level .99 was used to find the range of likely values for the true slope and true intercept of the model.

### Results For Part A
**ALL CODE USED TO OBTAIN THESE RESULTS CAN BE FOUND IN THE R CODE APPENDIX SECTION BELOW**
The coefficient of determination, r<sup>2</sup> is .5195. The estimated linear regression model was found to be ŷ = 47.5572 + 7.7389x. The ANOVA table associated with this model is shown in the appendix. The F-value associated with Regression(x) is 468.1992 with df1 = 1 and df2 = 433, (extremely large!), with p-value = 0, (extremely small!), so clearly reject the null hypothesis that the slope of the model is zero. The 99% CI for true intercept is (33.396625, 61.717823) and the 99% CI for true slope is (6.813604, 8.664285).

### Conclusions and Discussion For Part A
I rejected that the slope of the model is zero, so x has some value in predicting y. The coefficient of determination, r<sup>2</sup>, of the model was .5195 so 51.95% of the variation of y can be explained by the changes in x indicating a rather strong positive association between x and y and the scatterplot of the data supports this. The other 48.05% of the variation of the dependent variable is presumedly due to random variability or unidentified variables. The estimated linear regression model was ŷ = 47.5572 + 7.7389x. The residual plot of the data seems to support linearity and no significant lack of fit for the model. I conclude that the model, ŷ = 47.5572 + 7.7389x accurately describes the relationship between x and y. This is because the residuals of the data seem to show general random scatter with no clear pattern indicating linearity and no significant lack of fit. So based off the residual plot, I have to say that there is good support for ŷ = 47.5572 + 7.7389x being an accurate model for the relationship between x and y.

### R Code Appendix 
You can find the code I used here along with tables, plots, and other graphics:  
