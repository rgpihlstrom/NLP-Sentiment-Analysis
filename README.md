**Author**:[Russell Pihlstrom](mailto:rgpihlstrom@yahoo.com)

<img src="https://github.com/rgpihlstrom/Project4/blob/main/images/Title.png" width="800" height="300" />

## Overview: 86% Accuracy!

This project uses a Naive Bayes classifier & supervised learning method to classify approximately 3300 tweets as either positive or negative based on words present within each tweet.  By leveraging and learning from past pre-coded positive or negative tweets I was able to create a model that correctly classified each tweet with an accuracy score of <b><ins>86%.</ins></b>  The developed algorithm/“model” can be reused to classify future potential tweets that are captured in a similar fashion as employed on our training data.  

## Project Context
Below is a timeline of actual events that influenced the dynamics of the business problem outline below.   
<img src="https://github.com/rgpihlstrom/Project4/blob/main/images/Background1.png" width="800" height="300" />

Its March 5, 2011.  It's also one week before the kickoff of the big SXSW conference.  The SXSW conference is a major deal in the tech, film, and entertainment industries bringing together the best and the brightest from all respective fields.  This year is significant as Apple has decided to surprise the tech world by using the event to launch its new iteration of its iPad platform., the iPad2.  Apple is coming off a stream of successful launches and just launch its iPad1 approximately one year ago.  The Apple team is looking to outdo its previous launches and the Apple Brand Manager is looking to make a splash with the launch of the iPad2.  In addition to surprising the tech world by launching the iPad2 at the same time as the SXSW event Apple decided to create a temporary store just to sell the new iPad2's close to the event.  The creation of a temporary store was seen as  risky but exciting by the Apple team which, if successful, could be used again for future launches.

## Business Problem
Given the above context the Brand Manager at Apple is interested in the following:
-   **1. General Sentiment Surrounding the Apple Brand from Event Attendees**
-   **2. The Reception of the iPad2, its Launching at SXSW and Use of A Pop-up Store**
-   **3. Capture Consumer Feedback as Potential Innovation Regarding Apples Product Portfolio**
<br>

 
## Data

The data was comes from CrowdFlower via <a href="https://data.world/crowdflower/brands-and-product-emotions">data.world</a>. Human raters rated the sentiment in over 9,000 Tweets as positive, negative, or neither.  I focused this project on the positive and negative tweets associated with Apple/ Apple products.  The resulting dataset is the aforementioned 3300 classified tweets.  Furthermore, the data was captured via tweeter and was predominately from SXSW attendees from the year 2011. 

## Model Development Methods
This project uses the Crisp DM methodology to generate and optimize the published model.  Crisp DM requires blending business strategy, available data, and modeling techniques best suited to the business drivers.  Model development is and was very iterative.  I began by doing secondary research around the SXSW event along with getting a basic understanding of twitter data.  Along with the project requirements noted above, the following additional factors were considered during the modeling process:
-   **1. Data Imbalance**  The number of positive tweets is far greater than the negative tweets.  This creates a scenario that makes predicting negative tweets more difficult as there is not as many example words to train our model.  To overcome this challenge the SMOTE technique was used.  

- **2. Selection of Supervised Learning Classifiers**  Initially I tried several different types of classifiers, and even developed a RNN classifier using Bi-directional LSTM.  Given longer training times and less than desired accuracy scores I opted to reduce the complexity of the data and changed my classifier to Naive Bayes.  Naive Bayes has shown historical strength in text classification and its fast-training time makes it ideal for smaller dataset.

-   **3. Business Drivers: Accuracy as Primary Scoring Metric**  Given the opportunity to learn as much from negative tweets vs. positive tweets I used a balanced accuracy score as my success criteria over precision and or recall.


## Model Results (86% Detection)
After several iterations, and a thorough cleansing of the data the trained model obtained a training score of 87% and a testing score of <b><ins>(86%)</ins></b>.  This tight span is required to ensure the model was not overfitting and optimize the opportunity to reuse the model on future twitter data captured from SXSW attendees.

<img src="https://github.com/rgpihlstrom/Project4/blob/main/images/Testscores1.png" width="800" height="300" />
<br>
## Business Results/ Recommendations
As stated above the goal of the project was three-fold.  I have outlined and summarized the results of each area of interest below:

<h3>1. Overall Brand Sentiment Scores</h3>
<img src="https://github.com/rgpihlstrom/Project4/blob/main/images/BrandSummary.png" width="800" height="300" />

### Observations:
- Generating Buzz – See Tbl1. As evidenced in table 1, which shows the frequency of brand mentions, the Apple brand is the leading brand name being included within a tweet.  It is being mentioned more than 3X the second most mentioned brand google.   Table 2 shows counts of hashtags included in tweets vs. other brands and as you can see the Apple brand and or an Apple product is being mentioned at a higher rate than other trending topics.
- Sentiment Splits – From table 3 you can see how these tweets are classified.  As shown, 83% of the tweets containing/ pertaining to an Apple product are positive while only 17% are negative.
- Key Tweets – As shown, you can see the general types of tweets regarding the brand in a positive manner.  However, if you review the negative sentiment tweets, a lot of the negative thoughts are coming from panelist presenting at the conference, which is causes retweets vs. genuinely organic negative sentiments toward the brand.
Overall, the brand seems to be being reflected in a positive tone.

<h2>2. Reception of iPad2, Feedback on Launching at SXSW:</h2>
<img src="https://github.com/rgpihlstrom/Project4/blob/main/images/IpadLaunch.png" width="800" height="300" />

### Observations:
- Building on above, the reception of the iPad2 along with launching at the conference were received in a mostly positive manner.  90% of the tweets containing “iPad2” or “Store” within the tweet were deemed positive while only 10% were deemed negative.
***Positive Word Cloud***
Words like “launch”, “new”,” smart” were used in reference to the acceptance of selling the first iPad2’s at the conference at the pop-up store
***Negative Word Cloud***
Words like “line”, “camera”,” out” were used in reference to the long lines at the pop-up store, along with some early feedback that the camera on the iPad2 may not be at a quality level expected by consumers.  Also “out” was used in reference to the temporary store running out of inventory.


<h2>3. Consumer Feedback on Apple Products/ Opportunities for Innovation:</h2>
To better understand where potential areas for consumer feedback would be warranted, I first graphed each product and associated sentiments by product or brand.  

<img src="https://github.com/rgpihlstrom/Project4/blob/main/images/IphoneBatteryOverview.png" width="800" height="300" />

As you can see nothing stands out as too peculiar except the iPhone.  As you can see the iPhone is receiving almost 50% as many negative sentiments as positive sentiments.  Furthermore, in table 2 you can see that it relative percentage of negative tweets to total tweets is more than twice that of the other Apple products.
<br>

Based on this analysis I decided to do a deep dive on what is driving the higher-than-expected negative sentiments.  Shown below is a summary of that analysis.
<img src="https://github.com/rgpihlstrom/Project4/blob/main/images/IphoneBattery.png" width="800" height="300" />

### Observations:
My recommendations for innovation are focused on working to create additional solutions around the 4 most predictive features associated with churn which were noted above in point #1.
- Type of Contract – The goal is to reduce spontaneous churn.  If churn customers are not interested in a 1 year or a 2-year contract, perhaps there is a shorter term contract that can be created to induce trial.  Perhaps try 6 months or quarterly contracts.
- Method of Bill Pay -  Examine quality and/ or customer experience required to pay bill electronically.  Look to make this process as easy as possible.
- Increasing Months with Telco - Examine ideas for Innovation around loyalty programs to incent longevity
- Type of Internet Service -  Given the big difference in rate of churn across DSL vs. Fiber Optics churners, I believe there is something obviously wrong.  My recommendation is to engage in a competitive and or quality analysis to ensure the quality of the fiber optics lines are meeting customer expectations.

## Summary 

- **Brand In Good Health!
** - Given the above scores the brand health seems to be good with SXSW attendees that use twitter.

- **iPad2 Launch @ SXSW is a SUCCESS!
** - Consumers received the launching of the Ipad2 with open arms and excitement

- **Product Reviews Mostly Good!
** - Product reviews mostly good with a few areas we can take back to R&D for review, especially in regard to the iPhone battery.

## Next Steps

- **Broaden Dataset**
** - Broaden our data set, beyond conference goers and twitter users.  This project was solely focused on the Twitter data captured from SXSW conference attendees.  There is an opportunity to scape product sites and use that data to drive business value.
- **Examine Additional Classifiers/ Create Opportunity for Stacking Classifiers**
** - In this project I focused on Naive Bayer classifiers, but there are additional classifiers that work well on text data such as Random Forest.  Creating additional models and combining the models to make predictions can improve accuracy.
- **Finer Classification**
** - Look to create classifiers that can accurately classify Negative, Neutral, Positive tweets vs just Positive and Negative in this project.  Potentially perform Topic Modeling.




## For More Information

See the full analysis in the [Jupyter Notebooks](folder) or review our <a href="https://github.com/rgpihlstrom/Project3/blob/main/Presentation.pdf">Presentation</a>.

For additional info, contact me here: [ Russell Pihlstrom](mailto:rgpihlstrom@yahoo.com)
