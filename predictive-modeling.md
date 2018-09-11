## Predictive Modeling (19 questions)
#### 1. (Given a Dataset) Analyze this dataset and give me a model that can predict this response variable.
- For raw dataset, need to process the data first: validate data, clean data (such as deal with extreme data), data transformation and aggregation, and manipulate missing values.
- Explore data: identification of variables, different data types need different analysis methods, check multi-collinearity (regularization) and normality of the variables using correlation matrix, scatter plot, etc. If too many variables, it's better to consider dimension reduction, such as Principal Component Analysis (PCA).
- Determine if the problem is classification or regression
- Start by fitting a simple model (multivariate regression, logistic regression), do some feature engineering accordingly, and then try some complicated models. Always split the dataset into train, validation, and test dataset. Use cross validation to check their performance and use LASSO (L1 norm) for feature selection.
- Compare performance of multiple models with evaluatio metrics, e.g. MSE, MAE, weighted MSE, and tune model for better performance, such as change model parameter, add or delete features, and interation terms.
- Favor simple models that run quickly and you can easily explain.
- Visualize the data and the relationship between predictors and response and make a conclusion. 

#### 2. What could be some issues if the distribution of the test data is significantly different than the distribution of the training data?
- The model that has high training accuracy might have low test accuracy. Without further knowledge, it is hard to know which dataset represents the population data and thus the generalizability of the algorithm is hard to measure. This should be mitigated by repeated splitting of train vs test dataset (as in cross validation).
- When there is a change in data distribution, this is called the dataset shift. If the train and test data has a different distribution, then the classifier would likely overfit to the train data.
- This issue can be overcome by using a more general learning method.
- This can occur when:
  - P(y|x) are the same but P(x) are different. (covariate shift)
  - P(y|x) are different. (concept shift)
- The causes and potential solutions:
  - Sample selection bias: training samples are obtained in a biased way, such as non-uniform selection. And cross-validation can help to solve this problem.
  - Covariate shift: training and test input follow different distributions, but functional relation remains unchanged. And importance weighted cross-validation using Kernel Mean Match (KMM) can help to solve this problem.
  - Non-stationary environments: Training environment is different from the test one because of temporal or spatial changes. One typical scenario is adversarial classification problems, such as spam filtering and network intrusion detection. 
#### 3. What are some ways I can make my model more robust to outliers?
- We can have regularization such as L1 or L2 to reduce variance (increase bias).
- Changes to the algorithm:
  - Use tree-based methods instead of regression methods as they are more resistant to outliers. For statistical tests, use non parametric tests instead of parametric ones.
  - Use robust error metrics such as MAE or Huber Loss instead of MSE.
- Changes to the data:
  - Winsorizing the data (tansformation of statistics by limiting extreme values)
  - Transforming the data (e.g. log)
  - Remove them only if you’re certain they’re anomalies not worth predicting

#### 4. What are some differences you would expect in a model that minimizes squared error, versus a model that minimizes absolute error? In which cases would each error metric be appropriate? 
- Both MSE and MAE are used in predictive modeling.
- MSE had nice mathematical properties which makes it earier to compute the gradient, while MAE requires more complicated tools such as linear programming to compute the gradient. 
- Because of the square, large errors have relatively greater influence on MSE than do the smaller error. Therefor, MSE is more strict to having outliers. MAE is more robust in that sense, but is harder to fit the model for because it cannot be numerically optimized. So when there are less variability in the model and the model is computationally easy to fit, we should use MAE, and if that’s not the case, we should use MSE.
- MSE is more useful if we are concerned about large errors whose consequences are much bigger than eauivalent smaller ones. And MSE also corresponds to maximizing likelihood of Gaussian random variables.

#### 5. What error metric would you use to evaluate how good a binary classifier is? What if the classes are imbalanced? What if there are more than 2 groups?
- Accuracy: proportion of instances you predict correctly. Pros: intuitive, easy to explain, Cons: works poorly when the signal in the data is weak compared to the signal from the class imbalance. Also, you cannot express your uncertaintyabout a certain prediction.
- AUC (area under ROC curve): plot fpr on the x axis and tpr on the y axis for different threshold. Given a random positive instance and a random negative instance, the AUC is the probability that you can identify who's who. Pros: Works well when testing the ability of distinguishing the two classes, Cons: can’t interpret predictions as probabilities (because AUC only cares about the ranings of the prediction scores and not their actual values), so may not express the uncertainty about a prediction, or even the prebability that an item is successful.
- logloss/deviance: Pros: error metric based on probabilities,thus, estimates can be interpreted as prebabilities, Cons: very sensitive to false positives or false negatives when a lot of predictions that are near the boundaries.
- Other methods: F-score, Mean Average Precision, Cohen's Kappa, not as often used for general binary classification tasks, but may see them in specific subfields, e.g. F-score in NLP and Precision metrics in information retrieval.
- When there are more than 2 groups, we can have k binary classifications and add them up for logloss. Some metrics like AUC is only applicable in the binary case.

#### 6. What are various ways to predict a binary response variable? Can you compare two of them and tell me when one would be more appropriate? What’s the difference between these? (SVM, Logistic Regression, Naive Bayes, Decision Tree, etc.)
- Things to look at: N, P, linearly seperable?, features independent?, likely to overfit?, speed, performance, memory usage
- Logistic Regression
  - features roughly linear, problem roughly linearly separable
  - can turn most non-linear fetures into linear pretty easily
  - robust to noise, use l1,l2 regularization for model selection, avoid overfitting, low variance
  - the output can be interpreted as a probability
  - efficient and the computation can be distributed
  - a simple l2-regularized logistic regression can be used as a baseline for other algorithms
  - (-) can hardly handle categorical features
  - (-) high bias, tends to underperform when there are multiple or non-linear decision boundaries
  - (-) not fleible enough to naturally capture more complex relationships
- Support Vector Machines (SVM)
  - with a nonlinear kernel, can deal with problems that are not linearly separable (many kernels to choose)
  - good performance with high dimensional dataset, e.g. text classification
  - high accuracy, not biased by outliers
  - resistant to overfitting
  - (-) slow to train, for most industry scale applications (large number of features), not really efficient
  - (-) memory intensive
- Naive Bayes
  - computationally efficient when P is large by alleviating the curse of dimensionality (more features than observations)
  - works surprisingly well for some cases even if the condition doesn’t hold
  - with word frequencies as features, the independence assumption can be seen reasonable. So the algorithm can be used in text categorization
  - faset to train and predict, simple to implement
  - (-) conditional independence of every other feature should be met
  - (-) can be hampered by irrelevant features
  - (-) probabilistic estimates are unreliable because of naive assumption
  - (-) often outperformed by other models
- Tree Ensembles
  - do not expect linear features or even features that interact linearly
  - good for large N and large P, can deal with categorical features very well
  - non parametric, so no need to worry about outliers
  - Gradient Boosted Decision Trees (GBT) usually work better but are harder to get right (more hyperparameters to tune and more prone to overfitting), while Random Forest can almost work 'out of the box', but usually performs worse than GBT
  - (-) overfitting may occur, hard for interpretation
- Deep Learning
  - works well for some classification tasks (e.g. image, vedio, text)
  - used to squeeze something out of the problem

#### 7. What is regularization and where might it be helpful? What is an example of using regularization in a model?
- Regularization is a process of introducting additional information in order to solve an ill-posed problem or to prevent overfitting, including Ridge (shrink the magnitude of coefficients fastly), LASSO (least absolute shrinkage and selection operator, feature selection), and Elastic Net (combination of ridge and lasso).
- For example, we can use LASSO (l1) regularization in LASSO regression to penalize large coefficients.

#### 8. Why might it be preferable to include fewer predictors over many?
- When we add irrelevant features, it increases model's tendency to overfit because those features introduce more noise and the model will not do well with new data points. When two variables are correlated, they might be harder to interpret in case of regression, etc.
- Using too many features means getting more data, while it is not always possible to get all the data, so missing/sparse data can be very dangerous for the model performance.
- curse of dimensionality
- adding random noise makes the model more complicated but useless
- computational cost
- Methods to avoid the problem: reduce the number of features by manually selecting only required features or using a model selection algorithm; use regularization (LASSO).

#### 9. Given training data on tweets and their retweets, how would you predict the number of retweets of a given tweet after 7 days after only observing 2 days worth of data?
- Build a time series model with the training data with a seven day cycle and then use that for a new data with only 2 days data.
- Ask someone for more details.
- Build a regression function to estimate the number of retweets as a function of time t
- to determine if one regression function can be built, see if there are clusters in terms of the trends in the number of retweets
- if not, we have to add features to the regression function
- features + # of retweets on the first and the second day -> predict the seventh day
- https://en.wikipedia.org/wiki/Dynamic_time_warping

#### 10. How could you collect and analyze data to use social media to predict the weather?
- We can collect historical data from social media, such as twitter, Facebook, instagram API’s, based on location or social network. 
- Then define and label the weather in the past x days for each feed. 
- For each feed, find the words or phrase using with text matrix, for example, there may be some featured terms, like 'umbrella'. And feature reduction can be performed based on the weather information (only choose the highly frequent ones for a perticular weather).
- Find other possible attributes, such as date, location, etc.
- Extract the text and other attributes from the feed using National Language Processing (NLP) and then data manipulation.
- Build models with the historical data for a general weather prediction, such as KNN, Random Forest.

#### 11. How would you construct a feed to show relevant content for a site that involves user interactions with items?
- We can do so using building a recommendation engine. The easiest we can do is to show contents that are popular other users, which is still a valid strategy if for example the contents are news articles. To be more accurate, we can build a content based filtering or collaborative filtering. If there’s enough user usage data, we can try collaborative filtering and recommend contents other similar users have consumed. If there isn’t, we can recommend similar items based on vectorization of items (content based filtering).

#### 12. How would you design the people you may know feature on LinkedIn or Facebook?
- Find strong unconnected people in weighted connection graph
  - Define similarity as how strong the two people are connected
  - Given a certain feature, we can calculate the similarity based on
    - friend connections (neighbors)
    - Check-in’s people being at the same location all the time.
    - same college, workplace
    - Have randomly dropped graphs test the performance of the algorithm
- ref. News Feed Optimization
  - Affinity score: how close the content creator and the users are
  - Weight: weight for the edge type (comment, like, tag, etc.). Emphasis on features the company wants to promote
  - Time decay: the older the less important
  - more details: https://www.quora.com/How-does-LinkedIns-People-You-May-Know-work, https://www.quora.com/How-does-Facebooks-People-You-May-Know-work

#### 13. How would you predict who someone may want to send a Snapchat or Gmail to?
- for each user, assign a score of how likely someone would send an email to
- the rest is feature engineering:
  - number of past emails, how many responses, the last time they exchanged an email, whether the last email ends with a question mark, features about the other users, etc.
- People who someone sent emails the most in the past, conditioning on time decay.

#### 14. How would you suggest to a franchise where to open a new store?
- build a master dataset with local demographic information available for each location.
  - local income levels, proximity to traffic, weather, population density, proximity to other businesses
  - a reference dataset on local, regional, and national macroeconomic conditions (e.g. unemployment, inflation, prime interest rate, etc.)
  - any data on the local franchise owner-operators, to the degree the manager
- identify a set of KPIs acceptable to the management that had requested the analysis concerning the most desirable factors surrounding a franchise
  - quarterly operating profit, ROI, EVA, pay-down rate, etc.
- run econometric models to understand the relative significance of each variable
- run machine learning algorithms to predict the performance of each location candidate

#### 15. In a search engine, given partial data on what the user has typed, how would you predict the user’s eventual search query?
- Based on the past frequencies of words shown up given a sequence of words, we can construct conditional probabilities of the set of next sequences of words that can show up (n-gram). The sequences with highest conditional probabilities can show up as top candidates.
- To further improve this algorithm,
  - we can put more weight on past sequences which showed up more recently and near your location to account for trends
  - show your recent searches given partial data

#### 16. Given a database of all previous alumni donations to your university, how would you predict which recent alumni are most likely to donate?
- Based on frequency and amount of donations, graduation year, major, job type, income, etc, construct a supervised regression (or binary classification) algorithm.

#### 17. You’re Uber and you want to design a heatmap to recommend to drivers where to wait for a passenger. How would you approach this?
- Based on the past pickup location of passengers around the same time of the day, day of the week (month, year)
- Based on the number of past pickups
  - account for periodicity (seasonal, monthly, weekly, daily, hourly)
  - special events (concerts, festivals, etc.) from tweets
- Based on the above information, create frequency table, including location, frequency in certain time, then select the top K locations as recommend to drivers. 

#### 18. How would you build a model to predict a March Madness bracket?
- One vector each for team A and B. Take the difference of the two vectors and use that as an input to predict the probability that team A would win by training the model. Train the models using past tournament data and make a prediction for the new tournament by running the trained model for each round of the tournament
- Some extensions:
  - Experiment with different ways of consolidating the 2 team vectors into one (e.g concantenating, averaging, etc)
  - Consider using a RNN type model that looks at time series data.
- more details: https://arxiv.org/abs/1412.0248

#### 19. You want to run a regression to predict the probability of a flight delay, but there are flights with delays of up to 12 hours that are really messing up your model. How can you address this?
- This is equivalent to making the model more robust to outliers.
- See Q3.
