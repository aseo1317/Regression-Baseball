# No Runs No Problems

In my original prompt, I had submitted a proposal to look at which pitching statistics contributed most to winning percentage. However, I decided to change course by instead focusing on pitching statistics and the relationship they have with runs allowed. The rationale is this: if your team doesn't let the other team score, you will almost certainly win (unless your team also fails to do so but that is another discussion). I have scraped the necessary data from different sets of webpages on Baseball Reference and have done some preliminary analysis. 

![image](https://user-images.githubusercontent.com/89528655/135170321-5778e838-33e9-4067-ac3e-dc7819f9f572.png)

This first plot shows a simple linear relationship between hits allowed and runs allowed. As expected from the correlation chart, hits allowed seems to be a strong predictor of runs allowed. This data is in line with what we know about the subject matter. When a team allows more hits, they are allowing more opposing players to get on base and/or get the opponents closer to home base (run). For a simple regression, hits also scores decently well with an R^2 of 0.79.   

![image](https://user-images.githubusercontent.com/89528655/135170347-8711099a-d411-4434-a47c-a961b0dd0ece.png)
![image](https://user-images.githubusercontent.com/89528655/135170353-4bfe7887-e976-4c32-9154-da0131e81872.png)

Hits allowed was the first feature that I immediately wanted to examine because it is the most obvious (and often quickest) way to score runs. I next wanted to look at two other ways that result in getting on base: walks and errors. As seen above, these two plots aren't nearly as good predictors for runs as hits. 

While individually they may not prove to be strong predictors of runs, walks and errors still provide value to the model in conjunction with hits. The R^2 when walks is added as a feature increases to 0.833 and then to 0.835 with Errors.

My initial instincts seem to be pointing me in the right direction. However, there are many features still to test and the R^2 can definitely be improved. The first feature I intend to look at is slugging % (the total number of bases a player records per at-bat (hits only)) as this is a more robust version of hits. 

Next Steps:
- I need to take the next step in my modeling by coming up with a train/test/validation scheme (I most likely intend to use cross-validation).
- On first glance (and subject matter) I don't know if extensive feature engineering is necessary but will take a second look. 
- Regularization to find optimal alpha/lambda
- Test and Interpret 
