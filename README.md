# Project Midterm NEED TO EDIT

## Introduction/Background

Soccer, more commonly known as football in Europe and other parts of the world, is one of the most popular sports in the world, with over 1.5 billion people watching the FIFA World Cup final on television. Most approaches to solving the problem of scoreline prediction in soccer have involved match specific data restricted to past score lines, team lineups (which players played and how they performed), shots on target e.t.c. 

We would like to take a novel approach to solving this problem, by involving team specific data regarding playstyle that we took from the official FIFA video game coupled with game data. FIFA comes up with these metrics using the Ratings Collective, which is a scouting organization that observes league games from all over the world and develops detailed reports on players and teams. 

We will be using a training dataset that contains all match data played in major UEFA regulated leagues, team playstyle data from the 2008-2016 seasons. It has several features - - buildUpPlaySpeed, Team_id, matches - - among others that we have narrowed down to the most relevant ones in our methods section. 


## Problem Definition

Given two teams and all of their team attributes, we want to predict the outcome (win/tie/loss and scoreline) between a game played by them.

## Methods

### Data Cleaning
For every single team, we need to link together the team's attributes with how they performed against other teams and their attributes. While doing this, we will also need to choose which attributes are relevant to solving our problem. 
### Supervised Learning
We will potentially make use of Random Forest and Logistic Regression to do the supervised learning facet of our project to predict match outcomes based on our features and the corresponding predicted scoreline. 
### Unsupervised Learning
We can figure out what teams are similar in their playstyle using unsupervised learning. We can cluster based on the team attributes and performance to make groups of similar teams and then rank them. 

## Potential Results and Discussion

We can then test the accuracy of our model by comparing our predictions with actual results from games that have happened after 2016. This could also help us continue to improve our model until we reach a high level of accuracy. 

More specifically, we can use the following metrics:
- F1 score to see how well we predicted match outcomes (win/loss)
- Precision to see how accurate we are
- Explained variance to determine what attributes are determine the outcome and how good they are

## References

1. Predicting Final Result of Football Match Using Poisson Regression Model
2. Predicting the Outcome of Soccer Matches Using Machine Learning and Statistical Analysis
3. Predicting Winner of Football Match Using Analytical Hierarchy Process: An Analysis Based on Previous Matches Data

## Proposed Timeline

![Screenshot 2023-02-24 at 6 39 41 PM](https://github.gatech.edu/storage/user/46119/files/8380789a-3b14-48d8-abf5-ec3121f00273)

https://docs.google.com/spreadsheets/d/10YdRHSxJKPzC3VP-63NqZJo8fd-FwbrFPqzU63ccxqE/edit?usp=sharing

## Contribution Table

Navaneet: GitHub Page, Methods, Potential Results and Discussion, Video Presentation

Dhriti: Methods, Potential Results and Discussion, Video Presentation

Rishi: Introduction and Background, Problem Definition, Video Presentation

Tarun: Introduction and Background, Potential Results and Discussion

Nat: Problem Definition, Potential Results and Discussion, Video Presentation

## Checkpoint

A good checkpoint would be to have a basic model using supervised learning that can predict match outcomes. This is to ensure that our dataset is a good dataset, and we know how to utilize it to perform our desired analysis. 

## Works Cited

Azhari, H R, et al. “Predicting Final Result of Football Match Using Poisson Regression Model.” Journal of Physics: Conference Series, vol. 1108, Nov. 2018, p. 012066, https://doi.org/10.1088/1742-6596/1108/1/012066.


Elmiligi, Haytham, and Sherif Saad. “Predicting the Outcome of Soccer Matches Using Machine Learning and Statistical Analysis.” IEEE Xplore, 1 Jan. 2022, ieeexplore.ieee.org/document/9720896. Accessed 24 Feb. 2023.


Mathien, Hugo. “European Soccer Database.” Www.kaggle.com, 2017, www.kaggle.com/datasets/hugomathien/soccer.


Syaifudin, Yan Watequlis, and Pradini Puspitaningayu. “Predicting Winner of Football Match Using Analytical Hierarchy Process: An Analysis Based on Previous Matches Data.” IEEE Xplore, 1 Oct. 2021, ieeexplore.ieee.org/document/9655836. Accessed 24 Feb. 2023.
