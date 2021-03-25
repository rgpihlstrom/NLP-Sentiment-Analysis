**Author**:[Russell Pihlstrom](mailto:rgpihlstrom@yahoo.com)

<img src="https://github.com/rgpihlstrom/Project4/blob/main/images/Title.png"/>

## Overview: 86% Accuracy!

This project uses a Naive Bayes classifier & supervised learning methods to classify approximately 3300 tweets as either positive or negative based on the words present within each tweet.  By leveraging and learning from past pre-coded positive or negative tweets I was able to create a model that correctly classified each tweet with an accuracy score of <b><ins>86%.</ins></b>  The developed algorithm/“model” can be reused to classify future potential tweets that are captured in a similar fashion as employed on our training data set.  

## Project Context
Below is a timeline of actual events that influenced the dynamics of the business problem outline below.   
<img src="https://github.com/rgpihlstrom/Project4/blob/main/images/Background1.png"/>

Its March 5, 2011.  It is also one week before the kickoff of the big SXSW conference.  The SXSW conference is a major deal in the tech, film, and entertainment industries bringing together the best and the brightest from all respective fields.  This year is significant as Apple has decided to surprise the tech world by using the event to launch its new iteration of its iPad platform, the iPad2.  Apple is coming off a stream of successful launches and just launched its iPad1 approximately one year ago.  The Apple team is looking to outdo its previous launches and the Apple Brand Manager is looking to make a splash with the launch of the iPad2.  In addition to surprising the tech world by launching the iPad2, at the same time as the SXSW event, Apple decided to create a temporary "Pop-up" store to sell the new iPad2's close to the event.  The idea and impromptu creation of the temporary store was seen as risky but exciting, and if successful, could be used again for future launches.

## Business Problem
Given the above context the Brand Manager at Apple is interested in the following:
-   **1. General Sentiment Surrounding the Apple Brand from Event Attendees**
-   **2. The Reception of the iPad2, its Launching at SXSW and Use of A Pop-up Store**
-   **3. Capture Consumer Feedback as Potential Innovation Regarding Apples Product Portfolio**
<br>

 
## Data

The data was comes from CrowdFlower via <a href="https://data.world/crowdflower/brands-and-product-emotions">data.world</a>. Human raters rated the sentiment in over 9,000 Tweets as positive, negative, or neither.  I focused this project on the positive and negative tweets associated with Apple/ Apple products.  The resulting dataset is the aforementioned 3300 classified tweets.  Furthermore, the data was captured via tweeter and was predominately captured from SXSW attendees from the year 2011. 

## Model Development Methods
This project uses the Crisp DM methodology to generate and optimize the published model.  Crisp DM requires blending business strategy, available data, and modeling techniques best suited to the business drivers.  Model development is and was very iterative.  I began by doing secondary research around the SXSW event along with getting a basic understanding of twitter data.  Along with the project requirements noted above, the following additional factors were considered during the modeling process:
-   **1. Data Imbalance**  The number of positive tweets is far greater than the negative tweets.  This creates a scenario that makes predicting negative tweets more difficult for the model as there is not as many example words to train our model on what is negative vs. positive.  To overcome this challenge the SMOTE technique was used.  

- **2. Selection of Supervised Learning Classifiers**  Initially I tried several different types of classifiers, and even developed a RNN classifier using Bi-directional LSTM.  Given longer training times and less than desired accuracy scores I opted to reduce the complexity of the data and changed my classifier to Naive Bayes.  Naive Bayes has shown historical strength in text classification and its fast-training time makes it ideal for smaller dataset.

-  **3. Business Drivers: Accuracy as Primary Scoring Metric**  Given the opportunity to learn as much from negative tweets vs. positive tweets I used a balanced accuracy score as my success criteria over precision and or recall.


## Model Results (86% Detection)
After several iterations, and a thorough cleansing of the data the trained model obtained a training score of 87% and a testing score of <b><ins>(86%)</ins></b>.  This tight span is required to ensure the model was not overfitting and enable the opportunity to reuse the model on future twitter data captured from SXSW attendees.

<img src="https://github.com/rgpihlstrom/Project4/blob/main/images/Testscores1.png"/>
<br>

## Business Results/ Recommendations
<br>
As stated above the goal of the project was three-fold.  I have outlined and summarized the results of each area of interest below:

<h3>1. Overall Brand Sentiment Scores</h3>
<img src="https://github.com/rgpihlstrom/Project4/blob/main/images/BrandSummary.png" />

### Observations:
- <b><ins>Generating Buzz</ins></b> – See Tbl1. As evidenced in table 1, which shows the frequency of brand mentions, the Apple brand was the leading brand name being included within a tweet.  It is being mentioned more than <b><ins>3X</ins></b> the second most mentioned brand google.   Table 2 shows counts of hashtags included in tweets vs. other brands/ topics.  Notice the Apple brand and or an Apple products are being mentioned at a higher count than other trending brands/topics.

- <b><ins>Sentiment Splits</ins></b> – From table 3 you can see how these tweets are classified.  As shown, <b><ins>83%</ins></b> of the tweets containing/ pertaining to an Apple product are positive while only <b><ins>17%</ins></b> are negative.

- <b><ins>Key Tweets</ins></b> – As shown, the positive tweets regarding the brand are general in nature.  However, many of the negative tweets appear to be incited by panelist presenting at the conference vs. genuinely organic negative sentiments toward the brand.
<br>
Overall, the brand seems to be being reflected in a positive tone.

<h2>2. Reception of iPad2, Feedback on Launching and Selling at SXSW:</h2>
<img src="https://github.com/rgpihlstrom/Project4/blob/main/images/IpadLaunch.png" />

### Observations:
Building on above, the reception of the iPad2 along with launching and selling products at the conference were received in a mostly positive manner.  <b><ins>90%</ins></b> of the tweets containing “iPad2” or “Store” within the tweet were deemed positive while only <b><ins>10%</ins></b> were deemed negative.
<br>

- <b><ins>Positive Word Cloud</ins></b> - Words like “launch”, “new”,” smart” were used in reference to the acceptance of selling the first iPad2’s at the conference at the pop-up store

<br>

- <b><ins>Negative Word Cloud</ins></b> - Words like “line”, “camera”,” out” were used in reference to the long lines at the pop-up store, along with some early feedback that the camera on the iPad2 may not be meeting customers expecations on quality.  Also the word “out” was used in reference to the temporary store running out of inventory.


<h2>3. Consumer Feedback on Apple Products/ Opportunities for Innovation:</h2>
To begin my exploration of gathering consumer feedback, I first needed to review the product landscape and how the portfolio of products may or may not be receiving feedback.  I did so by plotting each product and associated sentiments.  

<img src="https://github.com/rgpihlstrom/Project4/blob/main/images/IphoneBatteryOverview.png" />

As you can see nothing stands out as too peculiar except the iPhone.  The iPhone is receiving negative sentiments at half the rate of positive tweets.  Compared to other Apple products this rate seems high.  Upon further analysis,  in table 2, you can see that its relative percentage of negative tweets received to its total tweets received is more than twice that of the other Apple products.
<br>

Based on these findings I decided to do a deep dive on what is driving the higher-than-expected negative sentiments.  
<br>
Shown below is a summary of results derived from a deep dive on the iPhone tweets.

<img src="https://github.com/rgpihlstrom/Project4/blob/main/images/IphoneBattery.png" />

### Observations:
- <b><ins>Word Cloud</ins></b> – Outside of the word “iPhone”, the next biggest word is “battery”.
- <b><ins>Key Tweets</ins></b> – Shown are just a few of the tweets mentioning the life of the iPhone battery as a major disappoint for consumers.
Based on these findings, we will make recommendations to the R&D teams for future develop!

## Summary 

- <b><ins>Brand In Good Health! </ins></b> - Given the above scores the brand health seems to be good with SXSW attendees that use twitter.
 
- <b><ins>iPad2 Launch @ SXSW and selling at Conference is a SUCCESS! </ins></b> - Consumers received the launching of the Ipad2 with open arms and excitement and the addition of the Pop-up store was well recieved.

- <b><ins>Product Reviews Mostly Good! </ins></b> - Product reviews were mostly good with a few areas we can take back to R&D for review, especially in regard to the iPhone battery.

## Next Steps
- <b><ins>Broaden our Data Beyond Conference Goers and Twitter Users</ins></b> - This project was solely focused on the Twitter data captured from SXSW conference attendees.  There is an opportunity to scrape other sites containing product data and use that data to drive business value.

- <b><ins>Examine Additional Classifiers/ Create Opportunity for Stacking Classifiers</ins></b> - In this project I focused on Naive Bayer classifiers, but there are additional classifiers that work well on text data such as Random Forest.  Creating additional models and combining the models to make predictions can improve accuracy.

- <b><ins>Finer Classification Models</ins></b> - Look to create classifiers that can accurately classify Negative, Neutral, Positive tweets vs just Positive and Negative in this project.  Potentially perform Topic Modeling.




## For More Information

See the full analysis in the [Jupyter Notebooks](folder) or review our <a href="https://github.com/rgpihlstrom/Project4/blob/main/Phase4Presentation.pdf">Presentation</a>.

For additional info, contact me here: [ Russell Pihlstrom](mailto:rgpihlstrom@yahoo.com)
