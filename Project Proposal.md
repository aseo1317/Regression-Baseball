# Defense Wins Championships

## Question
The saying in football is that "good offense beats good defense". While the validity of this statement has been debated over the years in football, I wondered how true the adage was in baseball. The crux of defense in baseball is the pitcher and that will be our main focus (although some of the metrics are affected by the other fielders). I will look to examine which pitching statistics correlate most with win percentage. Here I've decided to focus on the regular season as the playoffs often have an element of luck that may distort our data. With the right analysis, I could provide baseball teams the insight to target pitchers who excel at the statistics that correlate most with wins. 

## Data
I will be pulling my data from both baseball-reference.com and fangraphs.com via web scraping. The data will be in season by season increments going back 35 years to the 1985 season. A row of data should include a team, its win percentage and a variety of pitching statistics including ERA, WHIP, BABIP, K%, FIP, RA/G and others. My first inclination is that there will be a positive correlation with K% (percentage of batters faced that the team strikes out) as strikeouts ensure the batter will not get on base and thus not have the opportunity to score.  

## Tools
I intend to mostly use BeautifulSoup as both sites seem easily scrapable. I will clean the data with pandas in python and present visualization through Matlab, Seaborn, and potentially Tableau. I don't anticipate needing additional resources besides the datasets and the tools listed above. 

## MVP Goal:
The MVP should be an initial plot showing a positive linear relationship between one of the pitching metrics and win percentage. 
