# Project4

### List of Major Questions
- **1. Blending wored embendings with **  
- 
-   **1. Data Imbalance**  Early in the development process it was obvious that I was dealing with an imbalanced set of data (more information/ rows of data on non-churn customer vs. churn customer).  To ensure optimum identification my processes/ modeling would need to account for this imbalance.  I addresd this gap by first attempting the model using different weights and ultimately decided to do SMOTE(Synthetic Minority Oversampling Technique) to overcome this challenge.

- **2. Selection of Supervised Learning Classifiers**  Initially I tried several different types of classifiers, ranging from Logistic Regression, Naive Bayes, Gradient Boost, Ada, and XGBoost.  Ultimately, I decided to use <b><ins>Knn, Decision Trees and Random Forest</ins></b> , as these classifiers are non-parametric and are highly interpretable.  Interpretability, the disproportionate number of categorical features, along with being able to avoid addressing multicollinearity were the most influential factors in selecting which classifiers to implement for this project.
