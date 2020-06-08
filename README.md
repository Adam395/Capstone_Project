# Cave Johnson Approved: Prediction of Steam User Reviews from Metacritic Data  
**DSI-11 Capstone Project - Adam Cohen**

### Problem Statement:

Steam is the largest video game digital distribution platform in the world, with a 75% market share. Games on the platform are ranked by "meta-scores," a numerical value based on the review score from Metacritic, a curator score based on Steam's trusted reviewers, and a "user score," which holds the most weight, based on user reviews.  
  
Steam user reviews carry the most weight on the site. They are the first review shown, in a search they get their own unique icon, and only the user score is shown in the thumbnail preview on Steam's front page. Because of the weight given to User Reviews, a game's sales can be made or broken by the score given to it.  
  
We at Catalyst Consulting, as part of our full-spectrum services to developers and publishers, want to provide prediction services using a regression model for user reviews. Based on a game's metacritic scores, an aggregate value of professional reviewers' opinions, we will predict Steam user scores, allowing developers to appropriately budget for advertising and predict revenue models. Our metric of success will be RMSE.  
  
We will not be trying to account for scandal though: an otherwise excellent game with a high Metacritic score can have a terrible User Review score due to game scandals, as users "review bomb" the user score section with negative reviews and rants about the developer.

### Executive Summary:
I used two pre-existing datasets from Kaggle.com as the basis of my study: one consisting of Steam User behaviors, and one consisting of Metacritic review data. I additionally conducted an informal study of Steam reviewers, and manually imputed Steam review data into a .csv, to create a dataset composed of Metacritic review data, average playtime for games, and the Steam review scores. We then split this data into a training and holdout set, dividing on whether or not the game was listed on Steam's storefront.  
  
My parameter of interest was the "Review Percent Score" metric, which I used regression models to try to predict based on the metacritic review data and average playtime for the game, and assessed on Root Mean Squared Error, or RMSE, value. Our most successful model was a Linear Regression model, which had an RMSE of 10.47, or a prediction spread of just under 21 percentage points.  
  
Overall, I would not consider my model a successful tool for real-world deployment. 10 points is a very large value when it comes to reviews. However, in analyzing the data after predicting on the holdout set, we found that User Review Score wasn't a good barometer of whether or not a game would be a commercial success. There were many games that were "blockbuster" titles, but which were ranked below smaller-scale games.


### Table of Contents
[Problem Statement](#Problem-Statement)  
  
[Executive Summary](#Executive-Summary)  
  
[Table of Contents](#Table-of-Contents)  
  
[Data Dictionary](#Data-Dictionary)  
  
[Datasets](#Datasets)
  
[References](#References)
---

### Data Dictionary  
| Data Name | Data Type | Description |  
|---|---|---|  
| metascore | integer | The aggregate professional review score on Metacritic. |  
| name | object | The title of the given game. |  
| console | object | The platform the game is designed for (this value is always PC). |  
| userscore | float | The aggregate review score of semi-professional and normal players on Metacritic. |  
| release_date | datetime | The release date of the given game. |  
| review_percent_score | float | The second of two scoring metrics on Steam's back end. |  
| hours_played | float | The average time played by users. This value is 0 if the game wasn't included in the Hours Played dataset, else it is the average of all listed hours played for that title. |  
| meta_meta | float | The metascore and userscore multiplied together. This value was added to create additional weight to these metrics and improve model prediction accuracy. |  
| played_dummy | integer | A binary value indicating if a playtime was available for the given game. Created to add additional weight to the hours_played column, owing to its low correlation. |
  
### Datasets  
  
-**result.csv:** A dataset consisting of video games on multiple platforms and their associated Metacritic reviews.  
-**steam-200k.csv:** A dataset consisting of 199,999 random Steam platform users and their behaviors, such as purchasing a game, playing a game, and the associated amount of time they performed that action.
-**df_for_data.csv:** A proprietary dataset consisting of the result.csv dataset with three additional columns added for Steam app_id (a game's unique identification value), Steam user score, and Steam user percent score.  
   
### References  
A tremendous thanks to SteamDB developers xPaw and Marlamin, who helped me verify to confirm my app_ids matched their respective titles and scores. Additionally a huge thanks to SteamSpy developer Sergey Galyonkin, who kindly offered to help me automate data collection from his system, but didn't have the capacity to do it within the Capstone window.  
  
Additionally, a huge thanks to Steam users HendrickFalcon, Pyromancer, Najas, Lokeet, Milktea9, Spragoon, Chaella, Garflow, Prevengineer, Kyathil, AtlasBurden, DrunkPak, Citizen Khaelis, Chaunsay, Overdrive9, Runman, and Hexadrine. Their participation in my study and insight about user experience, rating games, "hours played", and in Pyromancer's case, the back end of Steam's system, were invaluable in helping select features when initially data collecting.  
  
Lastly, thank you to Dr. John Abel, whose experience with plotting data using matplotlib was invaluable when concepting visuals and playing with visual parameters for impact, as well as answering lots of questions about debugging graphs.  

**Outside Sources:**  
1) https://www.gamasutra.com/view/news/112269/Analysis_Valves_Lifetime_Retail_Sales_For_HalfLife_CounterStrike_Franchises.php  
2) https://en.wikipedia.org/wiki/List_of_best-selling_PC_games#cite_note-8  
3) https://en.wikipedia.org/wiki/World_of_Warcraft#:~:text=World%20of%20Warcraft%20was%20the,game%20franchises%20of%20all%20time  
4) https://en.wikipedia.org/wiki/Call_of_Duty:_Black_Ops_III#Sales  
5) https://en.wikipedia.org/wiki/Steam_(service)#:~:text=The%20Steam%20platform%20is%20the,of%20global%20PC%20game%20sales  
6) https://www.statista.com/statistics/321374/global-all-time-unit-sales-call-of-duty-games/#:~:text=One%20of%20its%20successors%2C%20Call,copies%20as%20of%20January%202020.  
7) https://www.kaggle.com/tamber/steam-video-games  
8) https://www.kaggle.com/destring/metacritic-reviewed-games-since-2000

