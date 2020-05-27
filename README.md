# Airbnb challenge: Which country will be the holiday destination for new users?

![](figures/Presentation.png)

Airbnb began in 2008 from the idea of two designers who want to share their spare rooms in their home to travelers and since that moment millions of hosts and travelers choose to create a free Airbnb account so they can list their space and book unique accommodation anywhere in the world. What makes unique Airbnb is the experience itself and the fact that hosts and travelers can share their passions and experiences in almost all the corners of the world. The challenge of my project is to build a predictive model that can accurately suggest the first destination of a new Airbnb User. All the processes involved, such as exploratory data analysis, feature engineering, data cleaning and the machine learning models have been divided into main sections in the notebook and the reader is advised to read it sequentially to have a complete understanding of the whole project. There are 12 possible outcomes of the destination country: 'US', 'FR', 'CA', 'GB', 'ES', 'IT', 'PT', 'NL','DE', 'AU', 'NDF' (no destination found), and 'other' and the users considered in this analysis are only USA citizens. 

### Contact details

Email: soledadmusella@gmail.com

LinkedIn: linkedin.com/in/soledad-musella-bb8665104

### Table of Contents: 

- [Technologies used]()
- [Executive Summary]()
- [Exploratory Data Analysis]()
- [Data Cleaning and Feature Engineering]()
- [Modelling]()
- [Future Improvements]()


### Technologies used

- Python
- Pandas
- Seaborn
- Matplotlib
- Numpy
- Scikit-learn

### Executive Summary

For this project I've taken inspiration from the competition launched by Airbnb and closed in 2016, using the data set related. As the competition was close, I decided to used different evaluators from the one suggested by it, the Normalized discounted cumulative gain (NDCG) because my goal was to go beyond the challenge itself. In this project a series of classifiers such as Logistic Regression, Decision Trees and KNN are trained and improved to give the best prediction and give Airnbn and similar companies useful insights to improve significantly their marketing strategies and therefore their profit.


### Exploratory Data Analysis

The very first step was to load the data available into Pandas Dataframe and extract basic information such as the distribution of the values, the nature of the values and the possible relationship between them. In particular I focused my research on understanding if there could be a gender-based preference for certain countries and if, as a result, gender could be a decisive feature correlated to the decision of whether to choose a country or another. I also created new columns by performing feature engineering to find out which are the days of the week in which is more likely to have new accounts created. Surprisingly the week-end days turned out to be the less active days in terms of creating new accounts. 

 ![](figures/Gender.png)                                                         ![](figures/Days.png)                                                                  

### Data Cleaning and Feature Engineering

I have been working on two datasets in particular, the first called "sessions" and the second called "users". Both of the datasets were row and with a huge number of null values. The data cleaning process was focused on solving the problems given by having null categorical values and trying to find the best way to handle them to avoid further bias during the modelig part. In addiction, to that I' ve been performing some future engineering by creating new variables( "day of the week", "first action", "last_action_detail" etc) and merging the data sets with new columns in one unique and meaningful final data set: "final_users".


### Modeling 

Predicting holiday destinations for new Airbnb users presents a very specific and unique problem: it is a multiclass classification. Due to the complexity of  the task and the short deadline, I decided to convert my multiclass classification into binary classification by dividing the target variable "countries_destination" in two classes: "US" and "no US". I picked "US" because performing the EDA I realized that the majority of the users were going on US on holiday. 
I decided to use 3 different models and I tuned them with hyperparameter: Logistic Regression, KNN and Decision Tree. By realising that I was having a class imbalance issue I use the SMOTE technique to resample my data and more accurate predictions. My winning model was the Logistic Regression tuned with hyperparameter because was the model that gave the best performance. However by performing my final prediction on the test set with this model I got a much lower result on the ROC_AUC metric.  This showed for sure some overfitting but also the lower result was a consequence of the fact that I didn't resample the test set with the purpose of having a more realistic result.

### Future Improvements

The data sets that I've used to perform my analysis have incredible potential in terms of information and consequently insights. Scaling the numerical predictors could improve significantly the model performance. In addition I would like to perform a Random Forrest classifier and compare its performance with the other models.

















