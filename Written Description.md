# Project Pedro
Andrew Seo

## Abstract
The genesis of this project came from the sports cliche "defense wins championships." Although the quote is from a football coach, it is applicable to some degree in most sports. In baseball, defense starts with the pitcher. so I set out to figure out what makes up the best pitchers in baseball. Eventually, I settled on ERA+ as my target. While regular ERA measures the amount of runs a pitcher allows per apperance (standardized to 9 innings), ERA+ compares a pitcher's run prevention ability to that of the league average and also adjusts for the ballpark. This allows for more fair comparability between players not only in this season but also prior (and future) seasons as well. I believe it gives a more complete picture of a pitcher's ability. Once I decided on this statistic, I scraped player data from Baseball Reference, cleaned it, and then went through the regression project workflow. This process involved repeatedly feature engineering, cross validating, and regularizing the model and then eventually testing to get final evaluation scores.   

## Design
The goal of this project was to determine which features had the greatest impact on ERA+ (positively or negatively). 
I focused on keeping features which had the most correlation with the target variable and in some cases engineering features to better correlate while also removing those features which had collinearity with other features. 

## Data
The datasets were all collected from Baseball Reference, an expansive database of baseball statistics. My features mainly came from the Advanced Pitching page while my target and some supplemental features came from the Standard Pitching page. Each row simply lists the player, his team and age, and a variety of numerical pitching metrics. The data collected was from this 2021 season. I felt it was appropriate to use this year's data because the season is almost finished (about 3 games left) and more appropriate than using last year's, which was a shortened 60 game season. 

## Algorithms
_Feature Engineering_
1. This could be considered Step 0 in a way, but I immediately removed some data that were irrelevant (Name/Team) or would exhibit multicollinearity (regular ERA, Win Probability Added).
2. Used correlation heatmaps and pairplots to further identify features that exhibited multicollinearity. 
3. Looked at pairplots and added transformed features and interaction features. 
4. Trained and scored on step 3 to determine effect on accuracy of model.
5. Performed steps 3 and 4 numerous times. 

_Models_
Simple linear regression was used to set a baseline. K-fold cross validation was used to continously tweak this baseline to raise the score. When I determined I had done as much feature engineering as possible, I used LassoCV and RidgeCV to check for overfitting and a final optimization (if existed) to the model. Using all three of simple, LassoCV, and RidgeCV also influenced model selection

_Model Findings_ 

R^2 of baseline: 0.4790833346759704
MAE of baseline: 24.29058669707774

R^2 of Linear Regression: 0.5443644201777438
MAE of Linear Regression: 22.96626622448453

R^2 on Lasso: 0.5703002423914983
MAE on Lasso: 18.629114139703088

R^2 on Ridge: 0.5368909357157498
MAE on Ridge: 19.607274120303252

## Tools
- Baseball Reference website for providing necessary statistics
- Beautiful Soup to webscrape from Baseball Reference
- Pandas and numpy for EDA
- SKlearn for regression
- Matplotlib and Seaborn for visualization

## Communication

Presentation of findings attached to this written description. This includes visualizations and conclusions. 
