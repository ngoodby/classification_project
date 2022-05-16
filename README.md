# Early Detection of Heart Disease
## Metis Classification Project

**Design** 

The goal of this project was to implement a classification model to predict whether someone is likely to have heart disease or a heart attack based on other health and lifestyle characteristics. This would allow for early detection and early intervention for individuals deemed likely to experience heart disease or attack. After engineering relevant categorical features and testing several baseline models, I tuned an XGBoost model and tested its performance on a holdout segment of the dataset. This modeling exercise also provides insight into feature importance in predicting heart disease or attack, which could be leveraged to design effective screening approaches for patients and to prioritize what information is most essential to gather to determine someone's risk of heart disease or attack. 

**Data**

The data was obtained from [Kaggle](https://www.kaggle.com/datasets/alexteboul/heart-disease-health-indicators-dataset) and comes originally from the [CDC](https://www.cdc.gov/brfss/annual_data/annual_data.htm). Thank you to Alex Teboul for his initial cleaning of the dataset. The codebook for the data can be found [here](chrome-extension://efaidnbmnnnibpcajpcglclefindmkaj/https://www.cdc.gov/brfss/annual_data/2015/pdf/codebook15_llcp.pdf). The dataset contains information on 22 different attributes for 253,680 individuals. Fe


**Algorithm**

*Feature Engineering*
1. Create binary indicator of whether someone has a college degree based of level of education response.
2. Create binary indicator of whether someone makes more than $50,000 annually.
3. Create binary indicator of whether someone reported having poor mental health in less than 15 of the past 30 days.
4. Create binary indicator of whether people report health as good, very good, or excellent (as opposed to poor or fair).

*Model*

A logistic regression, random forest, k-nearest neighbor, and an extreme gradient boosting model were tested and compared before tuning and finalizing an xgboost model for this classification problem. The entire dataset was split into 80/20 training vs holdout sets. Negative log loss scores were determined for various iterations of the model using 5-fold cross validation with the training dataset and those scores were used to guide the tuning process. A class weighted implementation of XGBoost was used to account for the imbalanced dataset. This was implemented using the scale_pos_weight parameter with the value used being the inverse of the class distribution.

**Tools**
- Numpy and Pandas for data manipulation
- Scikitlearn and XGBoost for modeling
- Matplotlib and Seaborn for visualizing

**Communication**
- Presentation slides summarizing the project and findings can be found here.
