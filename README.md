# Capstone-Project
Sparkify Customer Data analysis 
### Project Motivation 
"Udacity Capstone Project"
> Sparkify is a music  app similar to spotify and pandora.
> In current analysis, we will be using user behavior log data.
> outline of data : 
    - data includes basic  information about each user and thier interaction with Sparkify.
    - each user can have multiple entries.
    - data also include information on churned users i.e. users who unsubscribed/ cancelled the Sparkify subscription.
    
### Required Packages 
    - Pyspark 
    - Spark [ can use AWS or IBM cloud ] 
    - Matplotlib
    - Seaborn
    - pandas
### File Description : 
      ./mini_sparkify_event_data.json.zip  : compressed folder containing the mini dataset file.
         command : unzip the data before using.
         unzip ./mini_sparkify_event_data.json.zip  
         "mini_sparkify_event_data.json"   : the mini dataset file
      ./data_analysis.ipynb                : data analysis python notebook
 Blog Post : https://medium.com/@c.yesesri1/sparkify-costumer-data-analysis-b51ac37b4091  
    ------------------------------------------------------------------------------------------------------------  
### Data Overview : 
The dataset used in current analysis includes user basic details and each user interaction with the Sparkify service. Our goal is to build a model with optimal accuracy and low false positives, to identify costumers, who are likely to leave the service, so any additional promotions can be sent to avoid costumer churning.

The current data analysis was performed using Spark, any cloud or cluster can be used to perform the analysis instead of spark.

Churn Definition: when customers or subscribers stop doing business with a company or service. … Customer churn impedes growth, so companies should have a defined method for calculating customer churn in a given period of time

### Data Cleaning Steps : 
    1. Rows with empty user Ids and session Ids are filtered out
    2.duplicate "User IDs" and "page" information are dropped out
    Number of Churn labels in the dataset used for model training : 32
    Number of otherwise labels in the dataset used for model training : 110
 This unbalance between the train data labels, can affect model accuracy and performance.
 
 ### Data Exploration : 
     1. Among Non-Churned users, both male and female had listened to same number of songs per session.While, among churned users, males listened to slightly more songs per session than females.
     2. Mostly paid users tend to leave the service
     3. As expected churned users were registered for short time period to Sparkify
 ### Features : 
        1. Time since user registered
        2. Number of songs Listened
        3. Songs Liked
        4. Songs Unliked
        5. Songs lsitened per session 
        6. Gender 
        7. Duration of time for which songs were listened.
        
### Modelling :   
The data is split into train, test and validation dataset, to train the model, tested it on test and validation data sets. Cross  validation is used to pick the models best parameters, followed by model evaluation using accuracy and F1_score metrics.
Evaluation Metrics : 
    Accuracy ( measure of True Positives and True Negatives) represents how close a measure comes to its true value. This is important because poor data processing or human errors can lead to inaccurate results that are not very close to the truth. Precision (False Negatives and False Positives) is how close a series of measurements of the same thing are to each other. Thus, Accuracy and Precision metrics are used to evaluate the models in current analysis.
Models : 
    1. Logistic Regression
    2. Gradient Boosted trees and 
    3. Support Vector Machine
    models were used to build the model and the one that performs best is finalized.
    
### Discussion : 
Logistic Regression model, take lowest computational time but comparatively, Gradient Boost Trees model have optimal  prediction   accuracy and F1-score value on test and validation data sets. Hence, Gradient Boost Trees model is the final optimal model for identifying customer churn.
It should be noted that only small subset of data is used for modelling, predictions could be improved by using more relevant features and larger data.
### Hyper parameters Tunning for Final Model : 
The final GBT model identify likely churn customers with %accuracy and % F1-score.
### Suggested Improvements :
Model predictions can be further improved by, 
 1. Hyper parameter tuning. 
 2. Using training dataset with balanced labels.
 3. Trying other robust algorithms by referring to literature.
 
### Final Model : 
The final GBT model identify likely churn customers with %accuracy and % F1-score.
 
### Acknowledgements :
I would like to than Udacity for proviing the Study material , data and computational resources to  performing current data analysis, I could make use of the Data-science skills that I have learn through the course work and got an opportunity to practically work on Apache Spark. 
 

