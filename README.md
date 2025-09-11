# premier-league-club-investment-analysis-python

## Description
The data set contains information on all the clubs so far participated in all the premier league tournaments.

## Case Study
The management of the firm aims to invest in one of the top-performing club in the English Premier League. To aid in their decision-making process, the analytics department has been tasked with creating a comprehensive report on the performance of various clubs. However, some of the more established clubs have already been owned by the competitors. As a result, the firm wishes to identify the clubs they can approach and potentially invest to ensure a successful and profitable deal.


## Column name & description

- Club: Name of the football club
- Matches: Number of matches the club has played in the Premier League
- Wins: Number of matches won by the club in the Premier League
- Loss: Number of matches lost by the club in the Premier League
- Draws: Number of matches drawn by the club in the Premier League
- Clean Sheets: Number of matches in which the club has prevented the opposing side from scoring
- Team Launch: Year in which the club was founded
- Winners: Number of times the club has won the Premier League
- Runners-up: Number of times the club has finished as runners-up in the Premier League
- lastplayed_pl: Year in which the team last played in the Premier League


## Section A: Explore the Dataset
![image](https://raw.githubusercontent.com/AyishaRana/premier-league-club-investment-analysis-python/refs/heads/main/Output/1st%20five%20rows.png)
![image](https://raw.githubusercontent.com/AyishaRana/premier-league-club-investment-analysis-python/refs/heads/main/Output/last%20five%20rows.png)
- Upon examining the dataset, **we note that it consists of 11 columns**, with the first column containing the club name and the remaining 10 columns providing information on the club's performance in the Premier League. However, the data is not entirely clean. **The club column has numerical values attached to it, likely indicating a serial number, and the runners-up column has null values.**
- **Noticed inconsistencies in the TeamLaunch column**. While most clubs have a year mentioned, one club has a month & year mentioned instead. This inconsistency may cause problems in the analysis, and the column should be cleaned. **Furthermore, we observe that 	there are null values in the Winners column.**
- **We also notice that the data type for the Runners-up column is non-numeric (i.e., object type).** To perform any numerical analysis 	on this column, we will need to convert it to a numeric data type.
![image](https://raw.githubusercontent.com/AyishaRana/premier-league-club-investment-analysis-python/refs/heads/main/Output/data%20info.png)

## Section B: Clean the Dataset
#### Start with Club column
![image](https://raw.githubusercontent.com/AyishaRana/premier-league-club-investment-analysis-python/refs/heads/main/Output/1st%20five%20rows%202.png)
- the numbers have been removed from the front of each club name in the Club column, it has been cleaned and is ready to be used for analysis.
#### Winners column
![image](https://raw.githubusercontent.com/AyishaRana/premier-league-club-investment-analysis-python/refs/heads/main/Output/winners%20column%20info.png)
- Upon inspecting the dataset, **it can be observed that there are a total of 25 non-null values.** Furthermore, it is noteworthy that 	out of the 18 football clubs listed, none of them have won the Premier League title, as the Winners column displays a count of 0 for each club.	
- **After looking at the counts, it has been determined that there have been a total of 30 Premier League tournaments held in the past (1992-2022 per year one tournament). Out of the 25 football clubs (Non zero non nulls in winner columns) listed in the dataset, 3 clubs have won the Premier League title once, 1 club has won it thrice, 1 club has won it 5 times, another club has won it 6 times, and 1 club has won it a remarkable 13 times, totaling to 30 victories.**
- This implies that all other clubs in the dataset have not won any Premier League matches.
- Therefore, **updated the Winners column by replacing the null values with 0**, as these clubs have not won the Premier League title. 
#### Runners-up column 
![image](https://raw.githubusercontent.com/AyishaRana/premier-league-club-investment-analysis-python/refs/heads/main/Output/Runners-up%20column%20info.png)
- We noticed some inconsistency in data, **this column particularly has null values, 0's and '-' We need to clean.**
- Since we know the no. of times Premier League was conducted is 30 and we have data for all. so **converted the null & '-' to 0** for all other clubs.
- Also **'Runners-up' column is Object type, we converted it into int type.**

![image](https://raw.githubusercontent.com/AyishaRana/premier-league-club-investment-analysis-python/refs/heads/main/Output/data%20info%202.png)
#### TeamLaunch column
- Noticed inconsistencies in the TeamLaunch column. **While most clubs have a year mentioned, one club has a month & year mentioned instead.** 
- **converted the column to YYYY format.**
#### extracted only the year from lastplayed_pl column 
- because full date format is not needed for the analysis.

## Section C: Deep dive into Data Analysis
#### Calculate basic data summaries
![image](https://raw.githubusercontent.com/AyishaRana/premier-league-club-investment-analysis-python/refs/heads/main/Output/data%20summary.png)
-  **Observation:** 
- The average number of matches played by each team in the tournament is 573.75, while the mean number of goals scored by all teams is 769. However, the median number of goals scored is much lower at 462, indicating that some teams have scored 	significantly more goals than others.
- Interestingly, the median number of wins and runners-up positions are both 0, suggesting that most teams have not won or finished as runners-up in the tournament. However, **there is one team that has won the tournament a remarkable 13 times and another team that has been the runners-up 7 times.** It would be interesting to find out which teams these are.
- **upon analysis, We have found that Manchester United has won Premier league 13 times and have been runner-up 7 times.**
## Visualize each column
###### Start with Matches Played column
###### plot histogram
![image](https://raw.githubusercontent.com/AyishaRana/premier-league-club-investment-analysis-python/refs/heads/main/Output/Histogram%20of%20Matches%20Played%20column.png)
-  **Observation:** 
- We can see from the histogram that a majority of teams have played less than 400 matches. However, **there are a few teams that have played an exceptionally high number of matches, exceeding 900.**
- **As per the project requirements, it is worth noting that some of the more established clubs have already been owned by the competitors. Therefore, the client is interested in identifying potential clubs that may perform well in the future, even if they have less experience in the Premier League.**
###### Identified teams who have played more than 900 matches
![image](https://raw.githubusercontent.com/AyishaRana/premier-league-club-investment-analysis-python/refs/heads/main/Output/11%20clubs.png)
-  **Observation:** 
- Upon analysis, **we have observed that there are a total of 11 clubs who have significantly more experience in the Premier League as compared to the others.** These clubs have played a higher number of matches and have established themselves as experienced players in the league.
- As per the client's requirements, we are interested in identifying potential clubs that may perform well in the future, even if they have less experience in the Premier League. Therefore, **we have decided to drop these 11 clubs from our analysis, as their established presence in the league may skew our results and make it difficult to identify less experienced clubs with high 	potential.**
- By removing these clubs, we can focus our analysis on the remaining clubs and potentially identify hidden gems that may have been overlooked due to their lack of experience in the league.
###### Now, look at Win, Loss, Drawn, and clean sheets column
- To accurately analyze the performance of the teams, we must normalize the data by dividing the no. of wins, loss, drawn, clean sheet, goals by the number of matches played.
- This normalization will provide us with a fair idea of the winning, losing, draw, and clean sheet percentages of each team along with goals per match.
- Created new columns for Winning Rate, Loss Rate, Draw Rate, & Clean Sheet Rate
- Created a column for average goals scored per match
![image](https://raw.githubusercontent.com/AyishaRana/premier-league-club-investment-analysis-python/refs/heads/main/Output/Added%20columns.png)
###### Now visualize Winning, Loss, Drawn rate, and Clean Sheet
###### Create the boxplot
![image](https://raw.githubusercontent.com/AyishaRana/premier-league-club-investment-analysis-python/refs/heads/main/Output/Boxplot.png)
-  **Observation:** 
###### Winning Rate
It can be seen that **there are a few outliers in the Winning Rate boxplot,** which are located above the upper whisker. It is safe to conclude that these outlier clubs have shown exceptional high winning rates compared to the other clubs.
- **Upon analyzing the data, we have found that Leeds United and Blackburn Rovers are the two teams who have exceptionally high winning rates of 39% and 38% respectively.**
![image](https://raw.githubusercontent.com/AyishaRana/premier-league-club-investment-analysis-python/refs/heads/main/Output/High%20winning%20rate.png)

- Also **identified the club that has least "Winning Rate" is Hull City with lowest winning rate of 22%.**
![image](https://raw.githubusercontent.com/AyishaRana/premier-league-club-investment-analysis-python/refs/heads/main/Output/Loss%20rate.png)

###### Drawn Rate
We observe an outlier in the drawn rate boxplot, indicating that **there is one clubs has a much higher drawn rate compared to others.** This may not necessarily be a positive indication, as it suggests that the club may struggle to secure wins in their matches. So, identified which club is this.
 - Brighton & Hove Albion is expectionally high Drawn Rate of 33%
![image](https://raw.githubusercontent.com/AyishaRana/premier-league-club-investment-analysis-python/refs/heads/main/Output/Drawn%20rate.png)

###### Loss Rate
We can see very clearly that loss rates for these clubs are high compared to winning rate. 

###### Clean Sheet Rate
We see that data for Clean Sheet rate is pretty symmetric.
    
#### Next, Explored 'Winners' and 'Runners-up' columns
![image](https://raw.githubusercontent.com/AyishaRana/premier-league-club-investment-analysis-python/refs/heads/main/Output/winners%20column.png)
![image](https://raw.githubusercontent.com/AyishaRana/premier-league-club-investment-analysis-python/refs/heads/main/Output/Runners-up%20column.png)

- We observed that out of the 29 clubs, only 2 clubs have won the Premier League, and one club has been a runner-up.
- **Blackburn Rovers have won Premier League once and been an Runners-up once and Leicester City has won Premier League once.**
![image](https://raw.githubusercontent.com/AyishaRana/premier-league-club-investment-analysis-python/refs/heads/main/Output/Winners%20and%20Runners-up.png)
  
#### Next, looked at "lastplayed_pl" column
![image](https://raw.githubusercontent.com/AyishaRana/premier-league-club-investment-analysis-python/refs/heads/main/Output/last_played_pl%20info.png)
- Out of the total 29 teams, **eight are currently playing in the Premier League.** Since these teams are currently active in the league, it makes sense to prioritize them in our analysis. However, there are also teams that date back as early as 2000. It may be appropriate to assign these teams less weight.
##### Checked the eight teams that are currently playing in the Premier League
- Giving more priority to teams that have more recent experience playing in the Premier League is ideal. When making the final decision, we will assign higher weight to teams that have played more recently, and lesser weight to those that have not played recently.

![image](https://raw.githubusercontent.com/AyishaRana/premier-league-club-investment-analysis-python/refs/heads/main/Output/8%20clubs.png)
## Section D: Final Recommendations Framework
- created an empty Score column.
* Given a score of 10 if club have a relatively high experience in the 	Premier League above average (372)
* Given a score of 15 if club has winning rate above Q3
* Given a score of 15 if club has lossing rate below Q1
* Given a score of 10 if club drawn rate below Q1 and losing rate is below Q1
* Given a score of 10 if club has clean sheet above Q3 and winning rate is above Q3
* Given a score of 15 if club has won premier league
* Given a score of 10 if club has been a runners-up in premier league
* Given a score of 15 if club has been currently playing in premier league

![image](https://raw.githubusercontent.com/AyishaRana/premier-league-club-investment-analysis-python/refs/heads/main/Output/Scores%20column.png)
#### created a bar chart of team scores
![image](https://raw.githubusercontent.com/AyishaRana/premier-league-club-investment-analysis-python/refs/heads/main/Output/bar%20chart.png)
-  **Observation:** 
- **Based on the above chart, Blackburn Rovers has the highest score basis our analysis and next best Leicester City**
- checked the score of those clubs that have played in the last three years. Specifically, suggest including clubs that have played in 2023, as well as those that last played in 2022 and 2021.
- This approach helped to pinpoint those clubs that are currently in good form and have consistently performed well over the past few years.

![image](https://raw.githubusercontent.com/AyishaRana/premier-league-club-investment-analysis-python/refs/heads/main/Output/bar%20chart%20final.png)
- Upon closer examination of the list, we can observe that our current leader, Blackburn Rovers, is not included. To gain a better 	understanding of their performance, it's necessary to investigate further and determine the last year in which Blackburn Rovers played. This information will provide crucial context to our analysis and enable us to assess their recent form accurately.
- According to our research, Blackburn Rovers were relegated to the Championship league in 2012 i.e., league below Premier League and later to League One in 2017 i.e., league below Championship league. However, they were promoted back to the Championship in 	2018 and have since finished in the middle of the table in recent years. Given their inconsistent performance and lack of presence 	in the Premier League since 2012, it would be inappropriate to recommend this club for investment.
- On the other hand, Leicester City, the 2016 Premier League champions, have consistently finished in the top 10 in recent years. They placed 5th in both the 2019-2020 and 2020-2021 seasons and finished 8th in 2021-2022. Leicester City has the potential to 	achieve even greater success in the near future. Therefore, it would be reasonable to recommend Leicester City to our clients.
### We recommend investing in Leicester City based on our analysis



