# Midterm Report

## Introduction/Background: A quick introduction of your topic and mostly literature review of what has been done in this area. You can briefly explain your dataset and its features here too.

Soccer, more commonly known as football in Europe and other parts of the world, is one of the most popular sports in the world, with over 1.5 billion people watching the FIFA World Cup final on television. Most approaches to solving the problem of scoreline prediction in soccer have involved match specific data restricted to past score lines, team lineups (which players played and how they performed), shots on target e.t.c. 

We would like to take a novel approach to solving this problem, by involving team specific data regarding playstyle that we took from the official FIFA video game coupled with game data. FIFA comes up with these metrics using the Ratings Collective, which is a scouting organization that observes league games from all over the world and develops detailed reports on players and teams. 

We will be using a training dataset that contains all match data played in major UEFA regulated leagues, team playstyle data from the 2008-2016 seasons. It has several features - - buildUpPlaySpeed, Team_id, matches - - among others that we have narrowed down to the most relevant ones in our methods section. 

## Problem definition: Why is there a problem here or what is the motivation of the project?

Given two teams and all of their team attributes, we want to predict the outcome (win/tie/loss and scoreline) between a game played by them.

## Data Collection:

The data that we collected was directly sourced from a dataset from Kaggle as cited below, which contains the team attribute data and matches played in European Soccer from 2008-2016. The training set currently contains a sample of some of the matches played during this time period with the relevant statistics and we are currently testing our model on the remaining data. 

## Methods:

As mentioned before, our goal is to see which team would possibly win in a match given their play style attributes. To these ends, we first need to preprocess and clean the data as well as engage in feature selection. 

### Data Cleaning

To clean the data, we first sourced all the team specific attributes for each team and the matches played across the time period from the table. We then realized that there were a number of redundant columns that acted as classifiers for numerical values that were also within the team attributes table, for example, buildUpPlayPassing (int64) versus buildUpPlayPassingClass (discrete classification variable). The numerical team attribute values are a better indicator of the statistics, and therefore we eliminated the corresponding classification variable columns. 

However, for buildUpPlayDribbling, there is a lot of incomplete data, and therefore we made use of the class variable as it had complete values. Since this is a categorical feature, we used integer encoding (we will likely transition to one hot encoding later in the project).

We also noticed each team has multiple rows of statistics to highlight minor changes in team attributes from year to year. To standardize these statistics, we averaged them out since the overall deviation in attributes from year to year was deemed not significant enough. 

For every match, we then sourced the home team and away team attributes using a lookup function that we implemented. We then created another categorical feature to hold the match outcome (win/loss/draw)


![alt_text](https://github.gatech.edu/nkadaba3/MLProject/blob/main/Correlation.png)


This is a correlation table of the home team vs away team data for the matches we have. We can split this up into 4 quadrants like a coordinate grid. Q1 and Q3 are all very close to 0, and this makes sense because they are displaying the correlation of the home team’s statistics with the away team’s statistics. Q2 is home with home and Q4 is away with away. We can see darker colors here, which indicate stronger relations (either negative or positive). However, we can see that our range of correlation is not too high (highest value being 0.52), which indicates that each feature is relevant to the team’s playstyle and is important to characterize the team. One interesting note about the validity of our data is that defenceTeamWidth and defencePressure have a relatively high correlation of 0.52. This makes sense because logically speaking, the size of a team’s defense will affect how much pressure the team can apply. 

### Supervised Learning

We have so far implemented Logistic Regression. We plan to use random forest in the future to do the supervised learning facet of our project to predict match outcomes based on our features and the corresponding predicted scoreline. 

## Results and Discussion:

After data processing, we were able to update the missing features in our dataset with our lookup function. We then used PCA to engage in dimensionality reduction, for which the results are shown below. 

We ran our logistic regression model and our results were the following: 


```
Accuracy: 0.4828140703517588
Precision: 0.30788535262253797
Recall: 0.3822038982940909
F1-score: 0.31893260139375185
```


All our current metrics are below par. Our accuracy is below 50% which means that less than half the predictions we’re making are currently correct. Most importantly, our $F_1$ score is currently 0.3189. An acceptable $F_1$ score would at least have to be above 0.60, which means that our model is currently not performing well. The $F_1$ score that we have currently makes sense when looking at our low recall and precision. Precision is a fraction of the relevant instances among the retrieved instances. Recall is the fraction of the relevant instances that were retrieved. The F-score is a measure of the respective test’s accuracy and is calculated from a test’s precision and recall. The $F_1$ score which we are using, also called the balanced F-score, is the harmonic mean of the precision and recall. Since the harmonic mean of two numbers, $x_1$ and $x_2$ is defined as: $\dfrac{2}{\dfrac{1}{x_1} + \dfrac{1}{x_2}}$, the harmonic mean of recall and precision is: $\dfrac{2}{\dfrac{1}{recall} + \dfrac{1}{precision}}$

Since the precision and recall are from 0 to 1, the $F_1$ score must also be from 0 to 1. An $F_1$ score of 1.0 represents perfect precision and recall and a score of 0 means either precision or recall is 0.

![alt_text](https://github.gatech.edu/nkadaba3/MLProject/blob/main/Variance.png)

The figure above shows the pca explained variance ratio for respective components. This is one of the visualizations that we have created in order to showcase our data. 

![alt_text](https://github.gatech.edu/nkadaba3/MLProject/blob/main/PCABeforeAfter.png)

The figure above shows the scatter plot comparison of the first two pca components. The top graph shows the comparison before transformation and the bottom graph shows the comparison after transformation.


## Proposed Timeline

[https://docs.google.com/spreadsheets/d/10YdRHSxJKPzC3VP-63NqZJo8fd-FwbrFPqzU63ccxqE/edit?usp=sharing](https://docs.google.com/spreadsheets/d/10YdRHSxJKPzC3VP-63NqZJo8fd-FwbrFPqzU63ccxqE/edit?usp=sharing)

## Contribution Table

Nav: GitHub Page, Data Cleaning, Supervised Learning, Results and Discussion

Dhriti: Problem Definition, Data Collection, Results and Discussion

Rishi: Introduction and Background, Data Cleaning, Supervised Learning 

Tarun: Introduction and Background, Data Cleaning, Results and Discussion, 

Nat: GitHub Page, Problem Definition, Data Cleaning
