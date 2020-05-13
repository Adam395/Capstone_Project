# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 3: Datascraping and Modelling Subreddits

### Problem Statement:

Steam is the largest video game digital distribution platform in the world, with a 75% market share. Games on the platform are ranked by "meta-scores," a numerical value based on the review score from Metacritic, a curator score based on Steam's trusted reviewers, and a "user score," which holds the most weight, based on user reviews.  
  
Steam user reviews carry the most weight on the site. They are the first review shown, in a search they get their own unique icon, and only the user score is shwon in the thumbnail preview on Steam's front page. Because of the weight given to User Reviews, a game's sales can be made or broken by the score given to it.  
  
We at Catalyst Consulting, as part of our full-spectrum services to developers and publishers, want to provide prediction services for user reviews. Based on a game's metacritic scores, an aggregate value of professional reviewers' opinions, we will predict Steam user scores, allowing developers to appropriately budget for advertising and predict revenue models.  
  
We will not be trying to account for scandal though: an otherwise excellent game with a high Metacritic score can have a terrible User Review score due to game scandals, as users "review bomb" the user score section with negative reviews and rants about the developer.

### Executive Summary:



### Table of Contents
[Problem Statement](#Problem-Statement)  
  
[Executive Summary](#Executive-Summary)  
  
[Table of Contents](#Table-of-Contents)  
  
[Data Dictionary and Glossary](#Data-Dictionary-and-Glossary)  
[Glossary and Definitions](#Glossary-and-Definitions)  
[Data Dictionary](#Data-Dictionary)  
  
[Imports and Cleaning](#Imports-and-Cleaning)  
[Module Import](#Module-Import)  
[Data Import & Cleaning](#Data-Import-&-Cleaning)  
[Data Preparation](#Data-Preparation)  
  
[EDA](#EDA)  
[Generate "Common Words" Function](#Generate-"Common-Words"-Function)  
[Determining Keywords for Analysis](#Determining-Keywords-for-Analysis)  
[Possible Data Imbalance](#Possible-Data-Imbalance)  
  
[Model Generation and Selection](#Model-Generation-and-Selection)  
[Creating the X and y Variables](#Creating-the-X-and-y-Variables)  
[Baseline Model](#Baseline-Model)  
[Logistic Regression Models](#Logistic-Regression-Models)  
[Naive Bayes Models](#Naive-Bayes-Models)  
[Model Selection](#Model-Selection)  
  
[Model Evaluation](#Model-Evaluation)  
  
[Conclusions](#Conclusions)  
  
[References](#References)
---

### Dataset

