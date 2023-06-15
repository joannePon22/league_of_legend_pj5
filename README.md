# league-of-legends Model-Building
This is a project for DSC 80 at UCSD
by Joanne Pon and Justin Huang

Our exploratory data analysis on this dataset can be found on the website:
https://jnhuang02.github.io/League-of-Legends/
---

## Framing the Problem

We want to predict the result of whether the team will win or lose in the game. This will be a binary classification, since we are predict wheter win or lose. The response variable is the result column. We chose it becuase we think that prdicting a team will win or lose is important, if we can predict correctly, then that means we can find the factors that will lead to a team's lose or win, then the player can make changes to get a higher chance to win. The metrics we use is precision, recall, and f1-score. We chose these metrics, since it measure the proportion that we predict correctly, and this is suitable for our model.


---

## Baseline Model

We take in two columns, teamkills and teandeaths, which are both quantitative datas. These two columns represent the kills and deaths in the game. We want to use teamkills and teamdeaths to predict the result column by using ColumnTransformer and Stdscaler to build our Pipeline. For class '0', our precision: 0.96, recall: 0.95, F1-score:0.96, and for class '1', our precision: 0.96, recall: 0.96, F1-score: 0.96. In this performance, we can say that our current model is good, becuase the model has high precision, recall and F1-score. We also have a weighted average, it is also high(0.96).

---

## Final Model:

We add two features, total_gold and kd. We believe that adding these two values will increase the accuracy, since total_gold represent the resources amount the team obtain in the game. We believe that the higher the value in the total gold, the team will win the game more easier. Adding this feature, we think that can help us prdict the win or lose by considering the amount of gold the team have. Another feature, kill-to-death column represent the ratio of killing other and being killed, we think that it is obvious that if killing more people the team will be more likely to win the game, while having more times of being killed will decresed the chance of winning. We add those two features, to increase our accuracy, becuase we believe that they are important features that will affect the result. 

The modeling algorithm we chose is the RandomForestClassifier. 


---

## Fairness Analysis:

---


