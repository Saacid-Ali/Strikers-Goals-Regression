# Strikers-Goals-Regression
* Created a tool that predicts strikers goals in home/away games.
* Used a dataset from GitHub with Fantasy Premier League data.
* Utilised Linear Regression, Decision Tree and Random Forest Regressors to decide on the best model.

## Code and Resources Used 
**Python Version:** 3.7.6  
**Packages:** pandas, numpy, sklearn, matplotlib, plotly    
**Data Collection Source:** https://github.com/vaastav/Fantasy-Premier-League    
**View Code Files In Interactive Mode:** https://nbviewer.jupyter.org/

## Data Collection

The data was collected from https://github.com/vaastav/Fantasy-Premier-League. The dataset used was a fantasy premier league library that provided all the basic stats for each player as well as gameweek specific data and seasons history for each player. It includes the following:
* 4 seasons of data ranging from 2016/2017 to 2019/2020
* 2424 player seasons data
* Detailed match events (goals, assists, key passes, errors leading to goals and offsides)

This data collection contains data from the 2016/17 to the 2020/21 season. At the time this project was done the 2019/20 season was not complete. Therefore the data used was between the 2016/17 season to the 2018/19 season.

## Data Cleaning
Once the data was collected from the GitHub repository, the data needed to be cleaned prior to being used in the models. I made the following changes:

* Removed the redundant data on other positions such as goalkeepers and defenders.
* Removed redundant columns such as fixture information and fantasy premier league game data.
* Only the strikers that had played at least a minimum of 1710 minutes (19 games) were selected.
* Once this was done, the srikers stats for each game were totalled and were placed in one file.
* The totals for each striker were split into their totals for home and away games.
* Each striker's totals were converted into per 90 metrics.
* Per 90 metrics were used in this study as it gives as a more accurate representation of players performances. This is due to per 90 metrics showing each strikers performance in relation to their minutes played.
* Finally, the Home/Away columns were converted into an integer where 0 equals a home game and 1 equals an away game.

## EDA and Data Analysis
I looked at the distributions of the data and the value counts for the various categorical variables and also analysed the data to identify key trend. Below are a few highlights.

