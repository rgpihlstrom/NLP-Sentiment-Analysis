**Author**:[Russell Pihlstrom](mailto:rgpihlstrom@yahoo.com)

<img src="https://github.com/rgpihlstrom/Project4/blob/main/images/Title.png" width="800" height="300" />

## Overview: 86% Accuracy!

This project uses a Naive Bayes classifier & supervised learning methods to classify approximately 3300 tweats as either positive or negative based on words present within each tweet.  By leveraging and learning from past pre-coded positive or negative tweets I was able to create a model that correctly classified each tweet with an accuracy score of <b><ins>86%.</ins></b>  The developed algorithm/“model” can be reused to classify future potenital tweets that are captured in a simliar fashion as employed on our training data.  The data was comes from CrowdFlower via <a href="https://data.world/crowdflower/brands-and-product-emotions">data.world</a>. Human raters rated the sentiment in over 9,000 Tweets as positive, negative, or neither.  I focused this project on the positive and negative tweets associated with Apple/ Apple products.  The resulting dataset is the aforementioend 3300 classifed tweets.  Furthermore, the data was captured via tweeter asnd was predominately from SXSW attendees from the year 2011. 

## Project Context
Below is a timeline of actual events that influenced the dynamics of the business problem outline below.   
<img src="https://github.com/rgpihlstrom/Project4/blob/main/images/Background1.png" width="800" height="300" />
Its March 5, 2011.  It's also one week before the kickoff of the big SXSW conference.  The SXSW conference is a major deal in the tech, film, and entertainment industries bringing together the best and the brightes from all respective fields.  This year is significant as Apple has decided to surprise the tech world by using the event to launch its new iteration of its iPad platform., the iPad2.  Apple is coming off a stream of successfulll launches and just launch its iPad1 approximately one year ago.  The Apple team is looking to outdue its previous launches and the Apple Brand Manager is looking to make a splash with the launch of the iPad2. 







## Business Problem
Given the above context the Brand Manager at Apple is interested in the following:
-   **1. General Sentiment Surrounding the Apple Brand**
-   **2. The Reception of the iPad2, and its Launching SXSW vs. Historical Approaches**
-   **3. Capture Consumer Feedback as Potential Innovation Regarding Apples Product Portfolio**
<br>

#### The Current Situation: Telco is Losing 27% of Customers, 31% of Revenue to Churn.
<img src="https://github.com/rgpihlstrom/Project3/blob/main/images/TelcoChurnrates.png" width="600" height="400" />
<br>

### Business Questions Driving Model Development.
 The intended output of this theoretical business case is focused on helping Telco's CEO and Marketing leadership do the following:
-   **1. Identify Features Most Associated with Churn.**
-   **2. Evaluate Telco's Current offerings Ability to Prevent Churn.**
-   **3. Identify Areas for Potential Innovation.**
<br>
Furthermore, the model was developed for the purpose of reuse to identify and potentially prevent future customer churn for Telco.
 <br>
 
## Data

The data used for this project was provided by Telco and published and managed by Kaggle and served as a basis for past Kaggle competitions (Telco Customer Churn https://www.kaggle.com/blastchar/telco-customer-churn)  The dataset contains approximately 8k rows and 21 features capturing the purchase, usage, and tenure information on a subset of Telco's customers.  17 of the features are categorical, 3 are continuous, and 1 is ID.  A list of features contained within the data are below.
<br><br>
<img src="https://github.com/rgpihlstrom/Project3/blob/main/images/Columns.png" />

## Model Development Methods
This project uses the Crisp DM methodology to generate and optimize the published model.  Crisp DM requires blending business strategy, availabled data, and modeling techniques best suited to the business drivers.  Model development is and was very iterative.  I began by doing secondary research around the basic business drivers of the Telecom industry, gaining a better understanding on the prevalence of churn and the costs associated with fleeing customers.  Along with the project requirements noted above, the following additional factors were considered during the modeling process:
-   **1. Data Imbalance**  Early in the development process it was obvious that I was dealing with an imbalanced set of data (more information/ rows of data on non-churn customer vs. churn customer).  To ensure optimum identification my processes/ modeling would need to account for this imbalance.  I addresd this gap by first attempting the model using different weights and ultimately decided to do SMOTE(Synthetic Minority Oversampling Technique) to overcome this challenge.

- **2. Selection of Supervised Learning Classifiers**  Initially I tried several different types of classifiers, ranging from Logistic Regression, Naive Bayes, Gradient Boost, Ada, and XGBoost.  Ultimately, I decided to use <b><ins>Knn, Decision Trees and Random Forest</ins></b> , as these classifiers are non-parametric and are highly interpretable.  Interpretability, the disproportionate number of categorical features, along with being able to avoid addressing multicollinearity were the most influential factors in selecting which classifiers to implement for this project.

-   **3. Business Drivers: Churn Detection > False Alarms**  Recommendations on model development were based on secondary research along with working knowledge on the disparity between the cost to acquire vs the cost to retain customers.  In this hypothetical scenario, the CEO of Telco has asked me to place a particular focus on detection at the potential expense of unnecessary outreach activities.

<img src="https://github.com/rgpihlstrom/Project3/blob/main/images/ChurnOverFalseAlarms.png" width="600" height="300" />


## Model Results (85% Detection)
After several iterations, the below recall <b><ins>(85%)</ins></b>, accuracy <b><ins>85%</ins></b>, precision <b><ins>47%</ins></b>, and AUC<b><ins>82%</ins></b> scores were achieved for the selected classifier..  These results were acheived using the <b><ins>Random Forest Classifier</ins></b>.  It's important to remember these results were acheived with a focus on recall(detection) over precision (false alarms).
<br/>
<img src="https://github.com/rgpihlstrom/Project3/blob/main/images/ModelResults.png" width="600" height="400" />
<br/>
<h4>Results Explained (using below illustration):</h4>
<strong> - 85% Detection</strong> = Model Predicted Churn , Customer Actually Churned <br/>
<strong> - 34% False Alarms</strong> = Model Predicted Churn , Customer Actually remained Loyal<br/>
<strong> - 15% Undetected Churn</strong> = Model Predicted Loyal , Customer Actually Churned<br/>
<strong> - Red Dashed Line</strong> = This is our <b><ins>THRESHHOLD</ins></b> level (default probability rate) the model uses this % probability to label a customer as churn vs. not churn.<br/><br/>
<strong>***Key Take Away</strong> = Our model is very good at detecting churn.  As we decrease or increase our <b><ins>THRESHHOLD</ins></b> we can capture more or less churners.  This in turn results in a higher or lower False Alarm rate.  Per my suggestion in next steps below, we need to develop a cost for False Alarms.  This will allow us to create a profit tradeoff equation, enabling us to set the "right" threshold for the business.

<br>
<img src="https://github.com/rgpihlstrom/Project3/blob/main/images/VisualOfChurnDection.png" width="600" height="375"/>

<br><br>
## Business Results/ Recommendations (Using 50% Threshold)
As stated above the goal of the project was three fold.  I have outlined and summarized the results of each area of interest below:

<h3>1. Top Features Associated with Non Churn vs. Churn:</h3>
<img src="https://github.com/rgpihlstrom/Project3/blob/main/images/MostImportantFeatures2.png" />

### Observations:
- Type of Contract – 89% of churning customers are in Month-to-Month contracts.
- Method of Payment/ Billing – 55% of churning customers pay with electronic check.
- Months with Telco – 75% of churn is occurring within 29 months of becoming a Telco customer. 
- Type of Internet Service – 66% of churners are participating in the Fiber Optics Internet Service.

Together these factors were identified by the model as the 4 most predictive of churn.  To view a list of all the features used to develop this model see appendix in the pdf stored in this directory.  


<h2>2. Current Features/ Services Ability to Prevent Churn:</h2>
<img src="https://github.com/rgpihlstrom/Project3/blob/main/images/CountofEnrolledServices1.png"/>

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
