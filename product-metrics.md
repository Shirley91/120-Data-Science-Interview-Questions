## Product Metrics (15 questions)

#### 1. What would be good metrics of success for an advertising-driven consumer product? (Buzzfeed, YouTube, Google Search, etc.) A service-driven consumer product? (Uber, Flickr, Venmo, etc.)
  * Funnel: impression -> click -> conversion -> sale (may consider referral)
  * advertising-driven: Pageviews, daily actives
    * by impression (display-ads): CPM (cost per thousand impressions), RPI (revenue per impression)
    * by click (click-ads): CTR (click through rate), CPC (cost per click), RPC (revenue per click)
    * by conversion (not widely used): CVR (conversion rate)
    * ROAS (return on ad spend), ROI (return on investment)
  * service-driven: number of purchases
    * customer success: active users, CAC (customer acquisition cost), CVR (conversion rate), RCR (retention-churn ratio)
    * business operations: MRR (monthly recurring revenue), ARR (total annual recurring revenue), LTV (lifetime value)
    
#### 2. What would be good metrics of success for a productivity tool? (Evernote, Asana, Google Docs, etc.) A MOOC? (edX, Coursera, Udacity, etc.)
  * productivity tool: generally have base (free), premium (individual pay), and business (group pay) users.
    * daily active users, daily new users, TAD (total active days per user), CVR (conversion rate), RCR (retention-churn ratio), payment ratio, average revenue per user, etc.
  * MOOC: daily new users,daily active users, daily average online time, registered rate, completion rate
  
#### 3. What would be good metrics of success for an e-commerce product? (Etsy, Groupon, Birchbox, etc.) A subscription product? (Netfix, Birchbox, Hulu, etc.) Premium subscriptions? (OKCupid, LinkedIn, Spotify, etc.) 
  * e-commerce: number of purchases, conversion rate, Hourly, daily, weekly, monthly, quarterly, and annual sales, Cost of goods sold, Inventory levels, Site traffic, Unique visitors versus returning visitors, Average resolution time, CRR (customer retention rate), AOV (average order volume), LTV (lifetime value), ATC (add to cart ratio), brand name search, CAR (cart abandonment rate)
    * ads on e-commerce: CPA (cost per acquisition = ad spend / orders), RPC (revenue per click = revenue from ads / ads clicks)
  * subscription: daily active users, daily new users, churn or RCR (retention-churn ratio), MRR (monthly recurring revenue), ARPU (average revenue per user), SGR (subscriber growth rate based on month), CPA (cost per acquisition), LTV (lifetime value)
  * premium subscriptions: same to abive, CTR (click through rate), CPA (cost per acquisition, ROI (return on investment), etc.

#### 4. What would be good metrics of success for a consumer product that relies heavily on engagement and interaction? (Snapchat, Pinterest, Facebook, etc.) A messaging product? (GroupMe, Hangouts, Snapchat, etc.)
  * heavily on engagement and interaction: MAU/DAU (monthly/daily active users), daily average online time, page viewed per hour/day/week/month, number of engagements (including connections, new content, comments, shares, clickes and likes) per users per day/week/month, tap-throughs, opting in to push notifications, direct open rates, event conversions, interaction percentage
  * messaging product: MAU/DAU (monthly/daily active users), number of connections per users per day/week/month
  
#### 5. What would be good metrics of success for a product that offered in-app purchases? (Zynga, Angry Birds, other gaming apps)
  * Average Revenue Per Paid User vs. Average Revenue Per User, percent of users making an in-app purchase, daily average time in-app
  * metrics for mobile product (app):
    * customer activity: downloads, MAU/DAU (monthly/daily active users),session length (period time between app open and app close), session interval (frequency in which users open the app and how sticky the app is), time in-app
    * conversion and retention: CVR (conversion rate), churn, retention, RCR (retention-churn ratio), love score (based on the app's popularity, ratings and reviews, customer sentiment, reviewer quality, and Apptentive’s internal database with over 50 million mobile customers to compare)
    * revenue: download revenue for paid apps, in-app revenue, LTV (lifetime value)
    * team: quality of features released, timing of features released, team sentiment (team love score)
    
#### 6. A certain metric is violating your expectations by going down or up more than you expect. How would you try to identify the cause of the change?
  * breakdown the KPI’s into what consists them and find where the change is, then further breakdown that basic KPI by channel, user cluster, etc. and relate them with any campaigns, changes in user behaviors in that segment
  * Debugging metrics: for goal metrics based on multiple user behavior signals, it is helpful to keep track of how these individual signals contributed to the overall metric movement (and thus, it make a goal metric to be debuggable or decomposable)
  
#### 7. Growth for total number of tweets sent has been slow this month. What data would you look at to determine the cause of the problem?
  * Check if this problem is true. Compare the total number of tweets month-on-month (the past months in this year) and year-on-year (same month last year)
  * Funnal analysis: number of registed users, log-in users, active users, to check how many users registed then abandon, how many users logged-in but don't do anything increased. For active users, we need to check number of tweets posted per day/week and relations between number of tweets posted and users personal information and behaviors signals (e.g., age, device, region). 
  * Check spam accounts
  
#### 8. You’re a restaurant and are approached by Groupon to run a deal. What data would you ask from them in order to determine whether or not to do the deal?
  * for similar restaurants (they should define similarity), what's the deal (such as 10% off, a dish/drink for free, meal combo/value set), number of people use the deal, average increase in revenue gain per coupon, average increase in customers per coupon
  
#### 9. You are tasked with improving the efficiency of a subway system. Where would you start?
  * define efficiency
  
#### 10. Say you are working on Facebook News Feed. What would be some metrics that you think are important? How would you make the news each person gets more relevant?
  * rate for each action, duration users stay, CTR for sponsor feed posts, number of engagements (such as comments, shares, clickes and likes) per users per day/week/month,
  * ref. News Feed Optimization
    * Transposition score: how differently FB ordered your News Feed from the order you would have put stories if you had spent a few hours doing so.
    * Affinity score: how close the content creator and the users are
    * Weight: weight for the edge type (comment, like, tag, etc.). Emphasis on features the company wants to promote
    * Time decay: the older the less important
    
#### 11. How would you measure the impact that sponsored stories on Facebook News Feed have on user engagement? How would you determine the optimum balance between sponsored stories and organic content on a user’s News Feed?
  * Facebook's Sponsored Story is created within the Facebook Ad Platform and functions just like a Facebook Ad. You can set this up the same way as you set up Facebook Ads and select your targeting from the large list of available targeting and interest category options that Facebook provides. You'll create an ad image, write your ad copy, link to your content, assign a budget, set your bid, and then activate it. The main difference is that Sponsored Stories look like Facebook ads so they only appear in the right side of the Facebook Page where all the other ads are, and they will mainly target people who aren't fans of your Brand Page.
  * Check number of actions, CTR (click through rate), CPC (cost per click) by sponsored stories
  * Sponsored stories maily target people who aren't fans of your Brand Page, while organic content only targets to a small perentage of your fans, AB test should be conducted to determine the optimum balance between sponsored stories and organic content, the target metric could be CTR (click through rate), RPC (revenue per click), and MRR (monthly recurring revenue), etc.
  * Another one is promoted post, which can alse be used for improve user engagement. FB can distribute your content to a much broader segment of your fan based (the friends of people who interact with your post) instead of the fans who are already engaged with your brand.
  
#### 12. You are on the data science team at Uber and you are asked to start thinking about surge pricing. What would be the objectives of such a product and how would you start looking into this?
  *  there is a gradual step-function type scaling mechanism until that imbalance of requests-to-drivers is alleviated and then vice versa as too many drivers come online enticed by the surge pricing structure. 
  * I would bet the algorithm is custom tailored and calibrated to each location as price elasticities almost certainly vary across different cities depending on a huge multitude of variables: income, distance/sprawl, traffic patterns, car ownership, etc. With the massive troves of user data that Uber probably has collected, they most likely have tweaked the algos for each city to adjust for these varying sensitivities to surge pricing. Throw in some machine learning and incredibly rich data and you've got yourself an incredible, constantly-evolving algorithm.  
  * Uber leverages predictive modeling in real-time on traffic patterns, supply and demand. In short term, surge pricing substantially affects the rate of demand, while long-term use could be the key to retaining or losing customers. Customer backlash on rate-hiking is strong, so we can use machine-learning algorithms to predict where demand will be strong, so that drivers can adequately prepare to meet that demand, and surge pricing will be significantly reduced. 
  * More info about data analysis at Uber: (https://neilpatel.com/blog/how-uber-uses-data/)
  
#### 13. Say that you are Netflix. How would you determine what original series you should invest in and create?
  * Netflix uses data to estimate the potential market size for an original series before giving it the go-ahead.
  * For example, Netflix Saw that a good portion of their user base was interested in the 1990 British mini-series House of Cards, and saw that there wasn't anything currently in the market that was similar to that, then created a modern adaptation of it, casting Kevin Spacey and hiring David Fincher as a director, since they knew that people interested in House of Cards were also interested in programs with Spacey or Fincher.
  * More info: (https://www.salon.com/2013/02/01/how_netflix_is_turning_viewers_into_puppets/?123)
  
#### 14. What kind of services would find churn (metric that tracks how many customers leave the service) helpful? How would you calculate churn?
  * subscription based services
  * customer churn: percentage of suctomers that have churned, take all the customers you lose during a time frame, such as a month, and divide it by the total number of customers you had at the beginning of the month.
  * revenue churn: percentage of revenue that has churned, take all your monthly recurring revenue (MRR) at the beginning of the month and divide it by the monthly recurring revenue you lost that month minus any upgrades or additional revenue from existing customers. 
  
#### 15. Let’s say that you’re are scheduling content for a content provider on television. How would you determine the best times to schedule content?
  * check the time people watch TV, type of content they watch, and person info (such as age, sex, region), then based on the type of centent to schedule the time using classification models.
