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
Describe the modeling algorithm you chose, the hyperparameters that ended up performing the best, and the method you used to select hyperparameters and your overall model. Describe how your Final Model’s performance is an improvement over your Baseline Model’s performance.

We add two features, total_gold and kd. We believe that adding these two values will increase the accuracy, since total_gold represent the resources amount the team obtain in the game. We believe that the higher the value in the total gold, the team will win the game more easier. Adding this feature, we think that can help us prdict the win or lose by considering the amount of gold the team have. Another feature, kill-to-death column represent the ratio of killing other and being killed, we think that it is obvious that if killing more people the team will be more likely to win the game, while having more times of being killed will decresed the chance of winning. We add those two features, to increase our accuracy, becuase we believe that they are important features that will affect the result. 

The modeling algorithm we chose is the RandomForestClassifier. 
Best hyperparameters:  {'model__max_depth': 5, 'model__min_samples_split': 2, 'model__n_estimators': 200}
Accuracy:  0.9565423889812396
However, in our case, our performance doesn't have a big improvement.


---

## Fairness Analysis:
Clearly state your choice of Group X and Group Y, your evaluation metric, your null and alternative hypotheses, your choice of test statistic and significance level, the resulting p
-value, and your conclusion.

Our GroupX is teams with the most gold per gamme and the GroupY is the team that has the less gold per game. 
Our null hypothese is the model is fair for the team to take the most gold.
Our Alternative Hypothesis: There will be a difference beteen teams wih less gold and most gold.
Test statistic: precision difference betweem teams with less gold and more gold
significant level: 0.05

Observed Precision Difference:  0.03715830070213344
Null hypothesis is rejected, p value is :  0.001
Conclusion: The p-value is less than the significant value, so it suggests that the model's precision differs between groups.

---


