# SC1015 Mini-Project :  Analysis on Video Game Sales By FDDB Team 10

# Table of Contents
- Overview
- Requirements 
- Data preparation and cleaning
- Exploratory data analysis
- Machine learning models
- Contributors
- References

# Overview
This repository contains all the files for our SC1015 mini-project. With the increasing trend of video game sales, exarcerbated by COVID, we decided to showcase if video game sales can be determined by various factors (year, publisher, platform, review score, etc). The datasets we will be using are vgsales and all_games from kaggle.

# Requirements
The following modules are necessary for the code to run:
- numpy
- pandas
- seaborn
- matplotlib
- sklearn
- category_encoders
- xgboost

Disclaimer: The cells should be ran in sequential order. Do NOT re-run any cell after running all the cells for the first time, as the variables may have already been modified.

# Data preparation and cleaning
### Data Cleaning:
We removed the all the rows after 2016, as VGChartz (where the data for video game sales originated from) no longer produced estimates since 2018. From our observations, the number of titles in 2017 is unreliably small.
The next step involves removing any rows with missing values, followed by the merger of the 2 datasets based on the same name, year of release, and platform.

### Data Preparation:
To fully prepare the new combined dataset for analysis, we had to manually insert some games (Pokemon), as we noticed that Pokemon Games are exempted from the merger due to the difference in release years. Dataset 1 (video game sales) recognised the release year as the year it was released in Japan, while dataset 2 (video game ratings) recognised it as the year it was released in NA. Afterwards, we did a final clean by removing any rows with empty user review score or meta score. 

# Exploratory data analysis
EDA was conducted by plotting both numeric and categorical variables against the 3 different regional sales. It was to help us visualise the relationships between the different variables and the sales to do some preliminary analysis. Visualisation tools like boxplots, bar charts, and line plots were used to aid in the analysis. In the end, we plotted a major heatmap of all the numeric variables to find the correleations between them.

# Machine Learning Models
### Linear Regression
Linear Regression assumes a linear relationship between the predictors and the response. It was used to show how well it can linearly predict video game sales across the regions.We used regression metrics such as R^2 and MSE to gauge the accuracy and goodness of fit of the model. Our findings were not ideal, thus we engaged in other regression models.

### Random Forest Regression
Random Forest Regressor was used to predict video game sales, but the accuracy was not satisfactory. Despite tuning our model and finding the best hyperparameters to use using GridSearch, the error percentage of our prediction was still significant. We also computed the out-of-bag score, providing an unbiased estimate of our model's performance on unseen data, representing the accuracy of our model on out of bag samples.

### XGBoost
XGBoost was used to predict video game sales as well. Given a set of input features, XGboost regression constructs an ensemble of decision tree models, adding one tree to the ensemble at a time and fit to correct the prediction errors made by prior models, allowing us to perform predictive modelling for video games. We used GridSearch to tune our model by finding the best parameters as well, and found that this model could predict video game sales relatively well. 

# Conclusion
Out of the 3 models, XGBoost is the most successful in predicting video game sales. However, the metrics of mse, mae and r^2 were still significant, thus these models are not the best in predicting these sales. There could be other significant variables that plays a big part in predicting video game sales which we did not analyse. Having said that, we were able to somewhat predict these sales, and hence we conclude that these variables do affect salese.

# Contributors
- Lee Rei Ern, Joy (U2321787D) - EDA, Cleaning, Random Forest Regression, XGBoost, Analysis, Slides and Video Creation
- Yap Kwang Hwee (U2322493F) - EDA, Cleaning, Encoding, Linear Regression, Analysis, Slides and Video Creation

# References
- https://www.kaggle.com/datasets/gregorut/videogamesales/data
- https://www.kaggle.com/datasets/deepcontractor/top-video-games-19952021-metacritic
