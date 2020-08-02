# Severe Weather Prediction with Machine Learning

**Authors:** [Brea Beals](https://github.com/brbeals/), [Julian Kleindiek](https://github.com/ju-kl/), [Mark Roberts](https://github.com/markfroberts99/)

**Date:** June 2020

GitHub repository for our final project of the 'Machine Learning' course at the University of Chicago: https://github.com/ju-kl/severe-weather-prediction

**Business Problem:** Severe weather events caused >1,300 deaths and >$100B in damages from 2015 to 2020 in the US alone. For communities to better prepare for those events, our goal is to predict if a severe weather event is likely to happen in the near future and if so which type of event. For insurances to be able to allocate funds early and respond to those events quickly, our second goal is to predict the expected damage from severe weather events.

There are the following sections in our project:

### 1. Data Acquisition
- **01_data_preparation.ipynb**: In this notebook, we pull and prepare the data used in this project. We first download severe weather event data in the United States from [NOAA](https://www1.ncdc.noaa.gov/pub/data/swdi/stormevents/csvfiles/). We then download weather data in the United States from [Copernicus](https://cds.climate.copernicus.eu/cdsapp#!/dataset/reanalysis-era5-pressure-levels?tab=overview). At the end, both data sets are merged on a latitude-longitude-grid across the US.
- **01_data_manipulation.ipynb**: This notebook is an intermediate step in the data preparation notebook and was performed separately due to computational restrictions. The script select weather data from 2015-2020, increases the grid size by enlarging the distance between the unique values for latitude and longitude. It ultimately increases the granularity of our data.

### 2. Exploratory Data Analysis
- **02_exploratory_data_analysis.ipynb**: This script includes feature description, outlier identification & removal, exploration of severe Weather type and Impact, exploration into feature distributions, and correlation detection. 

### 3. Feature Engineering
- **03_feature_engineering.ipynb**: This notebook includes functions used to create features that will be used for modelling based on the data that was loaded from the web.

### 4. Data Modelling
- **04_severe_weather_prediction.ipynb**: This notebook uses machine learning techniques to compare the efficacy of training a binary classifier on unbalanced data vs on random undersampled data with a balanced 50/50 target variable proportion. For each data type, Logistic Regression, Random Forest, AdaBoost, and Gradient Boost models are utilized. Each model first is run through a hyperparameter grid search cross validation to identify the optimal estimator. Then. the model is further tuned by optimizing the prediction probability threshold to maximize recall while keeping precision at or above .1. Finally, all four models are combined into an ensemble model and ensemble predictions are recorded. After this process, the final test data performance is compared between the different model sets. 
- **04_severe_weather_classification.ipynb**: In this notebook, we apply different machine learning models to classify they type of severe weather event, given that a severe weather event has occured. The target variable is the class of severe weather event as defined by the EVENT_TYPE caegorical variable, and this notebook focuses on classifying the top three severe weather categories which make up 92% of the severe weather events: Thunderstorm Wind, Hail, and Flood. Prior data prepartation was done in the notebook '01_data_preparation.ipynb', and prior feature engineering and selection were done in the notebook '03_feature_engineering.ipynb'. We apply various models including Random Forest Classifier, Logisitc Regression Classifier, AdaBoost Classifier, KNeighbors Classifier, and XGBoost Classifier and compare their performance by examining the confusion matrix, normalized confusion matrix, and classfication report on both the test data and the training data. Principal Component Analysis and sampling techniques are applied to see if previous models can be improved. 
- **04_damage_prediction.ipynb**: In this notebook, we apply different machine learning and deep learning techniques to make predictions on the damage caused by severe weather events. The target variable will be a categorical variable created from DAMAGE_PROPERTY and DAMAGE_CROPS. We will use the feature engineered data resulting from previous notebooks. We start by classifying multiple damage categories based on balanced as well as unbalanced data. We apply models such as SVM, KNN, Decision Trees, Random Forests, Gradient Boosting, and Ada Boosting and compare their performance respectively.  We then limit the number of classes to only 2 and again make classifications based on balanced as well as unbalanced data. We apply deep learning techniques such as Artificial Neural Networks and benchmark them against machine learning models such as Ada Boosting and Gradient Boosting.
