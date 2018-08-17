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
  * breakdown the KPI’s into what consists them and find where the change is
  * then further breakdown that basic KPI by channel, user cluster, etc. and relate them with any campaigns, changes in user behaviors in that segment
#### 7. Growth for total number of tweets sent has been slow this month. What data would you look at to determine the cause of the problem?
#### 8. You’re a restaurant and are approached by Groupon to run a deal. What data would you ask from them in order to determine whether or not to do the deal?
  * for similar restaurants (they should define similarity), average increase in revenue gain per coupon, average increase in customers per coupon
#### 9. You are tasked with improving the e ciency of a subway system. Where would you start?
  * define efficiency
#### 10. Say you are working on Facebook News Feed. What would be some metrics that you think are important? How would you make the news each person gets more relevant?
  * rate for each action, duration users stay, CTR for sponsor feed posts
  * ref. News Feed Optimization
    * Affinity score: how close the content creator and the users are
    * Weight: weight for the edge type (comment, like, tag, etc.). Emphasis on features the company wants to promote
    * Time decay: the older the less important
#### 11. How would you measure the impact that sponsored stories on Facebook News Feed have on user engagement? How would you determine the optimum balance between sponsored stories and organic content on a user’s News Feed?
  * AB test on different balance ratio and see 
#### 12. You are on the data science team at Uber and you are asked to start thinking about surge pricing. What would be the objectives of such a product and how would you start looking into this?
  *  there is a gradual step-function type scaling mechanism until that imbalance of requests-to-drivers is alleviated and then vice versa as too many drivers come online enticed by the surge pricing structure. 
  * I would bet the algorithm is custom tailored and calibrated to each location as price elasticities almost certainly vary across different cities depending on a huge multitude of variables: income, distance/sprawl, traffic patterns, car ownership, etc. With the massive troves of user data that Uber probably has collected, they most likely have tweaked the algos for each city to adjust for these varying sensitivities to surge pricing. Throw in some machine learning and incredibly rich data and you've got yourself an incredible, constantly-evolving algorithm.  

#### 13. Say that you are Net ix. How would you determine what original series you should invest in and create?
  * Netflix uses data to estimate the potential market size for an original series before giving it the go-ahead.
#### 14. What kind of services would  nd churn (metric that tracks how many customers leave the service) helpful? How would you calculate churn?
  * subscription based services
#### 15. Let’s say that you’re are scheduling content for a content provider on television. How would you determine the best times to schedule content?
