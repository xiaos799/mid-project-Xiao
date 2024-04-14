# mid-project-Xiao

Steps:

Deal with missing values: 
1. impute with time series imputation, then keep only the recent 3 yr data
2. impute with KNN for each yr and test the primal KNN value via linear regression & r2 score --> maximum r2score test set 0.8372290370986162 at N 1

Observe country ranking over 3 yrs:
Identified 6 representative countries -- Afghanistan (at bottom in 3 yr), Finland (at top in 3 yr), Kuwait (rise to top in 3 yr), Yemen, Comoros & Sri Lanka (drop to bottom in 3 yr)

Observe correlations btw features:
There exist linear relations btw target variable and other variables --> safe to perform linear regression
Also high correlation btw life expectancy & GDP per capita --> use Lasso to test necessity to drop one

Put aside outliers -- as half of the outliers are among the top 10 countries, better to keep them but further test needed

Try out linear regressions/Lasso(alpha = 0.1) with/without outliers, different scalers --> robust scaler + outliers better
hyper parameter tuning --> alpha = 0 the best --> keep both GDP and life expectancy, correlation acceptable
Linear regression + robust scaler + outliers --> most important feature to happiness is social support

Logistic regression to predict happy or not:
Replace ladder life values -- 1 for 5+, 0 for 5-
SMOTE to balance classification of the target variable -- start with 2 then find the primal k = 16 with the highest f1 score

Confidence interval to see globally the proportion of happy countries

Test whether the result of regressions corresponds with the observations from the latest three yrs



Trello link:
https://trello.com/invite/b/VJRK4Zdl/ATTIc81447a34619a529d76ce30f5c39184967559673/xiao
