# Strikers-Goals-Regression
* Created a tool that predicts strikers goals in home/away games.
* Used a dataset from GitHub with Fantasy Premier League data.
* Utilised Linear Regression, Decision Tree and Random Forest Regressors to decide on the best model.
* Wrote a detailed report outlining the motivation for this study, the findings and the potential for future work.

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

![alt text](https://github.com/Saacid-Ali/Strikers-Goals-Regression/blob/master/fig1.png)
![alt text](https://github.com/Saacid-Ali/Strikers-Goals-Regression/blob/master/fig2.png)
![alt text](https://github.com/Saacid-Ali/Strikers-Goals-Regression/blob/master/Striker_Goals.png)
![alt text](https://github.com/Saacid-Ali/Strikers-Goals-Regression/blob/master/offsides.png)
![alt text](https://github.com/Saacid-Ali/Strikers-Goals-Regression/blob/master/cards.png)

## Model Building 

Firstly, I dropped some variables from the training data which included player_name, Season and the goals_scored_(per_90) variable. I also dropped other variables which were irrelevant including attempted_passes_(per_90) and completed_passes_(per_90). The test data only included the goals_scored_(per_90) variable as this is what I aimed to predict. 

Furthermore, I split the data into train and tests sets with a test size of 20%.  

I tried three different models and evaluated them using different metrics such as Model Score, Mean Absolute Error, Mean Squared Error and Root Mean Squared Error. I chose these different metrics because simply choosing one metric to evaluate the performance of these models does not paint the full picture of how well each model performed.

I tried three different models:
*	**Linear Regression** 
*	**Decision Tree** 
*	**Random Forest**  

Below is a graphic of the importance of each feature which found using Random Forest.

![alt text](https://github.com/Saacid-Ali/Strikers-Goals-Regression/blob/master/fig4.png)

## Model performance

The Linear Regression model was the best performing model and outperformed the other two models with a higher Model Score.

It also outperformed the other two models with a lower Mean Absolute Error, lower Mean Squared Error and lower Root Mean Squared Error.

The performance of the 3 models is evident in the figures below.

![alt text](https://github.com/Saacid-Ali/Strikers-Goals-Regression/blob/master/Metrics.png)
![alt text](https://github.com/Saacid-Ali/Strikers-Goals-Regression/blob/master/Model_Performance.png)


