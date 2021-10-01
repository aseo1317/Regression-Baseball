# Project Gala
Andrew Seo

Intro: 
Introduce yourself, why you care about the project you chose

Methodology: 
Could screenshot webpage scraped from
Insight into why the target was chosen/explain it
ERA+ histogram
ERA+ benefits:
Y/Y comparison, standarization of metric into whole number 

Maybe flowchart of process (e.g. IMDB scrape --> CSV --> EDA --> Regression)

Results: 
Slide 1 
General model fit (predicted vs. actual) 
R^2 and MAE results 

Slide 2
Bar chart/some graphic of coefficients and talk about some of the more relevant ones 

Conclusions: 

Future Work: 
Talk about methodologies you wanted to use as well as more features to examine

Appendix: 





## Abstract
The genesis of this project came from the sports cliche "defense wins championships." Although the quote is from a football coach, it is applicable to some degree in most sports. In baseball, defense starts with the pitcher. so I set out to figure out what makes up the best pitchers in baseball. Eventually, I settled on ERA+ as my target. While regular ERA measures the amount of runs a pitcher allows per apperance (standardized to 9 innings), ERA+ compares a pitcher's run prevention ability to that of the league average and also adjusts for the ballpark. This allows for more fair comparability between players not only in this season but also prior (and future) seasons as well. I believe it gives a more complete picture of a pitcher's ability. Once I decided on this statistic, I scraped data from Baseball Reference


We were hired by WTWY to aid them in obtaining signatures for their upcoming gala. Specifically, the focus was on optimizing the placement of their street team around the city. We used the turnstile data of subways publicly provided by NYC, focusing on total foot traffic based on entries and exits. We cleaned and orgnaized the data utilizing pandas in Python as well as SQLAlchemy and visualized this data on Matplotlib and Seaborn. These visuals allowed us to make an informed recommendation to WTWY and its street team.        

## Design
At its core, the goal of this projet is to maximize the potential signatures (and potential donations) the street team of WTWY can gather for its organization. We focused on organizing the data to determine which subway stations had the most entries and exits (and thus the most implied foot traffic). Another focus was to determine which days of the week had the most traffic and finally how the foot traffic of the busiest stations fluctuated depending on the day of the week.   

## Data
We almost exclusively used the dataset of MTA turnstile data obtained on the MTA website. Our data spanned over 3 months from 5/29/21 to 9/4/21, which contained 2.9 million rows of data. Each row represented a reading of a specific turnstile's **total entries and exits** up to the indicated point in time on that row. The initial data presented shows the turnstiles acting like odomoeters, simply counting up the total number of people passing through one way or the other. Some other notable columns included the SCP, C/A, and Unit codes, which in conjunction with Station name, represented a unique turnstile. 

## Algorithms
_Determining Top Traffic Stations_
1. Creating a new column called "Unique ID" comprised of C/A, Unit, and SCP
2. Finding the daily number of entries and exits using the difference between a day's maximum entries/exits and its minimum entries/exits
3. Filtering datapoints for outliers, specifically entries/exits that have extremely large values
4. Summing daily entries and exits to determine total traffic of a unique turnstile by day
5. Summing all of a station's foot traffic by day
6. Summing all of a station's total traffic during the observed period 

_Determining Top Traffic Days_

1-5 The same steps used to determine top traffic stations above

6. Add day of week column (Monday, Tuesday, etc.)
7. Summing total traffic by day of week  

## Tools
- MTA website to download the turnstile data and sanity check
- Exploratory data analysis using pandas, numpy, and SQLAlchemy
- Matplotlib and Seaborn for visualization

## Communication

Presentation of findings attached to this written description. This includes visualizations and recommendations. 
