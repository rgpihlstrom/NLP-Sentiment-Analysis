**Author**:[Russell Pihlstrom](mailto:rgpihlstrom@yahoo.com)

<img src="https://github.com/rgpihlstrom/Project4/blob/main/images/Title.png" width="800" height="300" />

## Overview: 86% Accuracy!

This project uses a Naive Bayes classifier & supervised learning methods to classify approximately 3300 tweats as either positive or negative based on words present within each tweet.  By leveraging and learning from past pre-coded positive or negative tweets I was able to create a model that correctly classified each tweet with an accuracy score of <b><ins>86%.</ins></b>  The developed algorithm/“model” can be reused to classify future potenital tweets that are captured in a simliar fashion as employed on our training data.  

## Project Context
Below is a timeline of actual events that influenced the dynamics of the business problem outline below.   
<img src="https://github.com/rgpihlstrom/Project4/blob/main/images/Background1.png" width="800" height="300" />

Its March 5, 2011.  It's also one week before the kickoff of the big SXSW conference.  The SXSW conference is a major deal in the tech, film, and entertainment industries bringing together the best and the brightes from all respective fields.  This year is significant as Apple has decided to surprise the tech world by using the event to launch its new iteration of its iPad platform., the iPad2.  Apple is coming off a stream of successfulll launches and just launch its iPad1 approximately one year ago.  The Apple team is looking to outdue its previous launches and the Apple Brand Manager is looking to make a splash with the launch of the iPad2. 

## Business Problem
Given the above context the Brand Manager at Apple is interested in the following:
-   **1. General Sentiment Surrounding the Apple Brand from Event Attendees**
-   **2. The Reception of the iPad2, and its Launching at SXSW**
-   **3. Capture Consumer Feedback as Potential Innovation Regarding Apples Product Portfolio**
<br>

 
## Data

The data was comes from CrowdFlower via <a href="https://data.world/crowdflower/brands-and-product-emotions">data.world</a>. Human raters rated the sentiment in over 9,000 Tweets as positive, negative, or neither.  I focused this project on the positive and negative tweets associated with Apple/ Apple products.  The resulting dataset is the aforementioend 3300 classifed tweets.  Furthermore, the data was captured via tweeter and was predominately from SXSW attendees from the year 2011. 

## Model Development Methods
This project uses the Crisp DM methodology to generate and optimize the published model.  Crisp DM requires blending business strategy, availabled data, and modeling techniques best suited to the business drivers.  Model development is and was very iterative.  I began by doing secondary research around the the SXSW event along with getting a basic understanding of twitter data.  Along with the project requirements noted above, the following additional factors were considered during the modeling process:
-   **1. Data Imbalance**  The number of positive tweets is far greater than the negative tweets.  This creates a scenario that makes predicting negative tweets more difficult as there is not as many example words to train our model.  To overcome this challenge the SMOTE technique was used.  

- **2. Selection of Supervised Learning Classifiers**  Initially I tried several different types of classifiers, and even developed a RNN classifier using Bi-directional LSTM.  Given longer training times and less than desired accuracy scores I opted to reduce the complexity of the data and changed my classifier to Naive Bayes.  Naive Bayes has shown historical strength in text classification and its fast training time makes it ideal for smaller dataset.

-   **3. Business Drivers: Accuracy as Primary Scoring Metric**  Given the opportunity to learn as much from negative tweets vs. positive tweets I used a balanced accuracy score as my success criteria over precision and or recall.


## Model Results (86% Detection)
After several iterations, and a thourough cleansing of the data the trained model obtained a training score of 87% and a testing score of <b><ins>(86%)</ins></b>.  This tight span is required to ensure the model was not overfitting and optimize the opportunity to reuse the model on future twitter data captured from SXSW attendess.

<img src="https://github.com/rgpihlstrom/Project4/blob/main/images/Testscores1.png" width="800" height="300" />
<br>
## Business Results/ Recommendations
As stated above the goal of the project was three fold.  I have outlined and summarized the results of each area of interest below:

<h3>1. Overall Brand Sentiment Scores</h3>
<img src="https://github.com/rgpihlstrom/Project4/blob/main/images/BrandSummary.png" width="800" height="300" />

### Observations:
- Type of Contract – 89% of churning customers are in Month-to-Month contracts.
- Method of Payment/ Billing – 55% of churning customers pay with electronic check.
- Months with Telco – 75% of churn is occurring within 29 months of becoming a Telco customer. 
- Type of Internet Service – 66% of churners are participating in the Fiber Optics Internet Service.

Together these factors were identified by the model as the 4 most predictive of churn.  To view a list of all the features used to develop this model see appendix in the pdf stored in this directory.  


<h2>2. Reception of iPad2, Feedback On Launching at SXSW:</h2>
<img src="https://github.com/rgpihlstrom/Project4/blob/main/images/IpadLaunch.png" width="800" height="300" />

### Observations:
- Building on above, the feature "Service Count" was not identified as a top predictor of churn.  Graphs show equal usage/ participation in services between loyal vs. churn customers.  However, ***66% of churners are enrolled in 3 or more services.***
Given that both groups are using services equally and the percent churn is not lower with increased service usage, I would deem that the services are not adequately helping to prevent customer churn.


<h2>3. Opportunities for Innovation:</h2>
<img src="https://github.com/rgpihlstrom/Project3/blob/main/images/Innovation3.png" />

### Observations:
My recommendations for innovation are focused on working to create additional solutions around the 4 most predictive features associated with churn which were noted above in point #1.
- Type of Contract – The goal is to reduce spontaneous churn.  If churn customers are not interested in a 1 year or a 2 year contract, perhaps there is a shorter term contract that can be created to induce trial.  Perhaps try 6 months or quarterly contracts.
- Method of Bill Pay  -  Examine quality and/ or customer experience required to pay bill electronically.  Look to make this process as easy as possible.
- Increasing Months with Telco - Examine ideas for Innovation around loyalty programs to incent longevity
- Type of Internet Service -  Given the big difference in rate of churn across DSL vs. Fiber Optics churners, I believe there is something obviously wrong.  My recommendation is to engage in a competitive and or quality analysis to ensure the quality of the fiber optics lines are meeting customer expectations.

The following 4 features were most predictive of churn: <strong>Month to Month Contract, Electronic Billing, Customer Tenure, and Fiber Optics Internet Service.</strong>

## Potential Impact on Revenue (Assuming 100% Detected Churn Reversal)
<img src="https://github.com/rgpihlstrom/Project3/blob/main/images/RevenueRamifications2.png" width="600" height="400"/>

### Observations:
- Today Telco experiences 27% customer churn rate which = 31% lost revenue.
- Given the <b>85% churn detection rate</b> generated by the model, Telco has an opportunity to reduce its churn to as little as 15% (for illustration purposes assuming 100% churn reversal).  The result of detecting and reversing the 27% historical rate of churn would result in a savings of 14% revenue.

## Next Steps

- **Develop Hard Numbers for the Cost of False Alarms** - In this hypothetical scenario we were not given the cost of falsely reaching out to a loyal customer with a particular outreach/ marketing program.  Once definitive numbers can be defined, we can reexamine our Threshold levels.
- **Develop Threshold Evaluation Formular** - Once aligned on costs and savings associated with churning customers,  a formula can be created to optimize economics between Detection vs. False Alarm.
- **Examine Detection vs. False Alarm Tradeoffs** - Given the high cost of customer acquisition vs. customer retention some additional analysis may reveal lowering our threshold from 50% to perhaps 40%, which would capture additional undetected churners.
- **Examine Additional Classifiers** - For this project I settled on Random Forest, however, given advances in classifiers such as extreme boost and others, there may be additional opportunities to improve our churn detection rates.
- **Put Model(s) Into Productions** - Once we have optimized our models and/or generated enough models to account for the wide variety of churn data, I would look to automate and deploy the models via a web-based interface and make it available to the marketing and or customer service teams.

## For More Information

See the full analysis in the [Jupyter Notebooks](folder) or review our <a href="https://github.com/rgpihlstrom/Project3/blob/main/Presentation.pdf">Presentation</a>.

For additional info, contact me here: [ Russell Pihlstrom](mailto:rgpihlstrom@yahoo.com)
