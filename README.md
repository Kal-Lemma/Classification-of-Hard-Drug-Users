# Classification-of-Hard-Drug-Users

## Drugs Consumption Data Set:
* 1,885 records
* 12 Personal Measurement attributes (examples; scores on extraversion, impulsiveness, ...)
* Drug Usage activity of 18 different Legal and Illegal Drugs (examples: chocolate, alcohol, weed, heroin) based on 7 classes of Never Used, Used in the Last Decade, Year, Month, Week, or Day.

## Exploratory Data Analysis
* Assigned ‘Labels’, turning values numeric, had no Missing values
* Removing Bias from liars in the ‘Semer’ column (A Fake Drug used in the study to catch dishonesty)
* Cleaned and created dummy variables for Gender and Lived in the U.K. since 55% of the dataset are from the United Kingdom.

## Feature Engineering
### Indicator / Interaction features
1. Created a Hard Drug binary column of whether you have ever done Crack, Heroin, or Ketamine.
2. Age: Classified into three categories of Young, Middle-Aged, Old
3. Education: had multiple selections for years attained, chose baseline column for whether they made it to College, indicator variable
4. Nicotine: indicator whether person smoked in past year
5. WeakDrugUse: Interaction feature summing use for legal ‘weaker’ drugs

## Feature Selection
* Used sklearn extra trees classifier for feature importance to indicate the top 10 performers in my interaction features
* * Using inbuilt class feature_importances of tree based classifiers to see the top 10 performers: Cocaine leading the charge.
![Screen Shot 2019-08-20 at 11.35.15 AM](https://github.com/klemma14/Classification-of-Hard-Drug-Users/blob/master/Data%20Visuals%20/Screen%20Shot%202019-08-20%20at%2011.35.15%20AM.png)

## Visualizing for better understanding
* ![Screen Shot 2019-08-20 at 11.34.26 AM](https://github.com/klemma14/Classification-of-Hard-Drug-Users/blob/master/Data%20Visuals%20/Screen%20Shot%202019-08-20%20at%2011.34.26%20AM.png)
* ![Screen Shot 2019-08-20 at 11.34.46 AM](https://github.com/klemma14/Classification-of-Hard-Drug-Users/blob/master/Data%20Visuals%20/Screen%20Shot%202019-08-20%20at%2011.34.46%20AM.png)
* The second picture shows that nearly half the people who have taken Hard drugs (Heroin, Ketamine, or Crack), and also went to college. Seems that it may be less likely to say no to drugs, without a college education.

## Numerous Models for best F1
![Screen Shot 2019-08-20 at 11.46.28 AM](https://github.com/klemma14/Classification-of-Hard-Drug-Users/blob/master/Data%20Visuals%20/Screen%20Shot%202019-08-20%20at%2011.46.28%20AM.png)
* Random Forest had the best Performance with F1 accuracy score.
![Screen Shot 2019-08-20 at 11.46.50 AM](https://github.com/klemma14/Classification-of-Hard-Drug-Users/blob/master/Screen%20Shot%202019-08-20%20at%2011.46.50%20AM.png)
* This Confusion Matrix shows the number of type I and II errors the model achieved. It managed to incorrectly classify 29 individuals as Hard Drug Users, when they never have.

## HyperParameter Tuning
* Used a randomized Gridsearch for classifier parameters, which seemed to not improve original top score.
* XGBoost for Randomforest which managed to bring original RMSE of __0.406__, down to __0.334__ for our testing set.

## Take aways
