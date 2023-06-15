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
Describe your model and state the features in your model, including how many are quantitative, ordinal, and nominal, and how you performed any necessary encodings. Report the performance of your model and whether or not you believe your current model is “good” and why.

We take in two columns, teamkills and teandeaths, which are both quantitative datas. These two columns represent the kills and deaths in the game. We want to use teamkills and teamdeaths to predict the result column by using ColumnTransformer and Stdscaler to build our Pipeline. 

---

## Final Model:
State the features you added and why they are good for the data and prediction task. Note that you can’t simply state “these features improved my accuracy”, since you’d need to choose these features and fit a model before noticing that – instead, talk about why you believe these features improved your model’s performance from the perspective of the data generating process.

Describe the modeling algorithm you chose, the hyperparameters that ended up performing the best, and the method you used to select hyperparameters and your overall model. Describe how your Final Model’s performance is an improvement over your Baseline Model’s performance.


---

## Fairness Analysis:
Clearly state your choice of Group X and Group Y, your evaluation metric, your null and alternative hypotheses, your choice of test statistic and significance level, the resulting p
-value, and your conclusion.

Optional: Embed a visualization related to your permutation test in your website.

Tip: When making writing your conclusions to the statistical tests in this project, never use language that implies an absolute conclusion; since we are performing statistical tests and not randomized controlled trials, we cannot prove that either hypothesis is 100% true or false.

---


