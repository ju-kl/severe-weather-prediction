# Severe Weather Prediction with Machine Learning

**Authors:** [Brea Beals](https://github.com/brbeals/), [Julian Kleindiek](https://github.com/ju-kl/), [Mark Roberts](https://github.com/markfroberts99/)
**Date:** June 2020

GitHub repository for our final project of the 'Machine Learning' course at the University of Chicago: https://github.com/ju-kl/severe_weather_prediction

**Business Problem:** Severe weather events caused >1,300 deaths and >$100B in damages from 2015 to 2020 in the US alone. For communities to better prepare for those events, our goal is to predict if a severe weather event is likely to happen in the near future and if so which type of event. For insurances to be able to allocate funds early and respond to those events quickly, our second goal is to predict the expected damage from severe weather events.

There are the following sections in our project:

### 1. Data Acquisition
- **01_data_preparation.ipynb**: In this notebook, we pull and prepare the data used in this project. We first download severe weather event data in the United States from [NOAA](https://www1.ncdc.noaa.gov/pub/data/swdi/stormevents/csvfiles/). We then download weather data in the United States from [Copernicus](https://cds.climate.copernicus.eu/cdsapp#!/dataset/reanalysis-era5-pressure-levels?tab=overview). At the end, both data sets are merged on a latitude-longitude-grid across the US.
- **01_data_manipulation.ipynb**: This notebook is an intermediate step in the data preparation notebook and was performed separately due to computational restrictions. The script select weather data from 2015-2020, increases the grid size by enlarging the distance between the unique values for latitude and longitude. It ultimately increases the granularity of our data.

### 2. Exploratory Data Analysis
- **02_exploratory_data_analysis.ipynb**: This script ... @Mark

### 3. Feature Engineering
- **03_feature_engineering.ipynb**: This notebook includes functions used to create features that will be used for modelling based on the data that was loaded from the web.

### 4. Data Modelling
- **04_severe_weather_prediction.ipynb**: This script ... @Mark
- **04_severe_weather_classification.ipynb**: This script ... @Brea
- **04_damage_prediction.ipynb**: In this notebook, we apply different machine learning and deep learning techniques to make predictions on the damage caused by severe weather events. The target variable will be a categorical variable created from DAMAGE_PROPERTY and DAMAGE_CROPS. We will use the feature engineered data resulting from previous notebooks. We start by classifying multiple damage categories based on balanced as well as unbalanced data. We apply models such as SVM, KNN, Decision Trees, Random Forests, Gradient Boosting, and Ada Boosting and compare their performance respectively.  We then limit the number of classes to only 2 and again make classifications based on balanced as well as unbalanced data. We apply deep learning techniques such as Artificial Neural Networks and benchmark them against machine learning models such as Ada Boosting and Gradient Boosting.
