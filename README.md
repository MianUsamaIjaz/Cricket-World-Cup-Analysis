# ICC Men's T20-Cricket World Cup 2022 Data Analytics
![ICC men's t20](images/t20.jpeg)

## Problem Statement :

In This project I created a Power BI Dashboard which helps to review and compare performances of all the players in T20 Men's Cricket World Cup 2022 tournament. This dashboard also enables us to select the best 11 of the tournament based on their performance based on defined selection criteria which is included as a part of problem statement.

## Datasource :

Scrapped all the data regarding match and world cup from www.espncricinfo.com and all details of player career performace.

## Data Collection:
Scrapped all the data regarding match and world cup and all details about players career with Python using Beautiful Soup, Selenium and Jupyter Notebook. Converted the json files into the dataframes and then these dataframes into csv file for further data analysis on Power BI.

## Data Transformation:
Performed initial data cleaning after scrapping such as player name correction, handle missing value, match id linking etc. using Pandas. Transformed the final data for dashboard using Power Query of Power BI.

## Data Modelling:
Connected all the datasets with based on some defined primary keys such as team and match ids. Also, created many measures, calculated columns and parameters for data analysis and dash boarding using DAX.

## Data Analysis Expression (DAX)
Measures used in visualization are:

- Total Runs = `SUM(t20_batting_summary[runs])`

- Total Innings Batted =`COUNT(t20_batting_summary[matchID])`

- Total Innings Dismissed = `SUM(t20_batting_summary[Out])`

- Batting Avg = `DIVIDE([Total Runs],[Total Innings Dismissed],0)`

- Total balls faced =`SUM(t20_batting_summary[balls])`

- Strike rate = `DIVIDE([Total Runs],[total balls faced],0)*100`

- Batting Possition = `ROUNDUP(AVERAGE(t20_batting_summary[battingPos]),0)`

- Boundary % = `DIVIDE(SUM(t20_batting_summary[Boundary runs]),[Total Runs],0)*100`

- Avg. balls faced = ` AVERAGE(t20_batting_summary[balls])`

- wickets = `SUM(t20_bowling_summary[wickets])`

- Balls Bowled = `SUM(t20_bowling_summary[balls])`

- Runs Conced = `SUM(t20_bowling_summary[runs])`

- Economy = `DIVIDE([Runs Conced],([Balls Bowled]/6),0)`

- Bowling Strike Rate =`DIVIDE([Balls Bowled],[wickets],0)`

- Bowling Avrage = `DIVIDE([Runs Conced],[wickets],0)`

- Total Innings Bowled = `DISTINCTCOUNT(t20_bowling_summary[matchID])`

- Dot Ball % =` DIVIDE(SUM(t20_bowling_summary[zeros]),SUM(t20_bowling_summary[balls]),0)`

- Player selection = `if(ISFILTERED(t20_players_info[name]),"1","0")`

- Display Text = `if([Player selection] = "1"," ","Select Player(s) by clicking the player's name to see their invidual or combined strength")`

- Color Callout Value =`if([Player selection]="0","#E8D166","#1D1D2E")`

- boundary runs batting =`t20_batting_summary[fours]*4 + t20_batting_summary[sixes]*6`

- boundary runs bowling =`t20_bowling_summary[fours]*4+t20_bowling_summary[sixes]*6`

## Reports:
Data visualization for the dataset was done using Microsoft Power BI Desktop:

### Player Analysis 

|    Openers      |
| --------------- |
|![2022 T20 Cricket World Cup Dashboard- Best Final 11-2](images/openers.png)|


 | Middle Order |
 | --------------- |
|![2022 T20 Cricket World Cup Dashboard- Best Final 11-3](images/middle_order.png)|


 | Finisher |
 | --------------- |
|![2022 T20 Cricket World Cup Dashboard- Best Final 11-4](images/finisher.png)|


| All Rounder |
| --------------- |
|![2022 T20 Cricket World Cup Dashboard- Best Final 11-5](images/all_rounder.png)|


| Specilist Fast Bolwers |
| --------------- |
|![2022 T20 Cricket World Cup Dashboard- Best Final 11-6](images/fast_bowler.png)|


| Final Best 11 Players |
| --------------- |
|![2022 T20 Cricket World Cup Dashboard- Best Final 11-8](images/best_11.png)|


## Tools, Software and Libraries :

1.Jupyter Notebook

2.Python

3.Pandas

4.Webscraping

5.Beautiful Soup

6.Selenium

7.Power Query Editor

8.Power BI
