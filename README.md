##  Regression Project Write-Up

**Abstract**

The goal of this project was to predict the TripAdvisor review score of hotels (between 1-5 stars) based on certain features of the hotel, using a linear regression model built from data scraped from current TripAdvisor hotel listings in Australia. The final linear regression model using Elastic Net has a negative mean absolute error (NMAE) of -0.32 and a mean R^2 score of 0.37.

**Design**

The focus of this project is on the hotels located in Australia’s top vacation destinations. Insights from this analysis can help hotel management and investors, as they can see which areas are worth focusing on to improve the popularity of their hotel. This project aims to identify specific features (or lack thereof) that contribute most to rating score. 

**Data**

Hotel data used to train the model was scraped from the hotels listed on the Tripadvisor website under the “Featured Destinations” section of Australia’s Vacation Rentals. The initial dataset consisted of 1316 hotels after removing duplicates. After iterative cleaning to remove null data during the feature engineering steps for modeling, the final dataset contained 571 hotels. For each hotel, data were collected for: Hotel Name, Featured Price, Category, Address/Location, Property Amenities, Room Features, Room Types, Hotel Style, Languages, Hotel Star Class, Car/Walkability score, Restaurants Proximity, Attractions Proximity, Number of Reviews, and Covid Precautions.

**Algorithms**

A thorough exploratory data analysis was performed, to clean and preprocess the data. Categorical variables were converted to binary dummy variables, with one dummy variable dropped from each category to avoid the dummy variable trap. The featured price was imputed using other numerical data such as Hotel Star Class and Number of Reviews. To trim down the features, regression models used to regularize the data (Lasso, Ridge, Elastic Net) were used to compute R^2 and NMAE via a 5-fold cross-validation process for each. The Elastic Net model was ultimately chosen for final feature selection and testing. Additional data transformations, such as box-cox transformations and interaction terms, were tried but ultimately not used in the final model. 

**Tools**

- Selenium and Beautiful Soup for webscraping 
- Numpy and Pandas for data analysis/cleaning
- Scikit-learn and statsmodels for building, training, cross-validating, and testing the model
- Matplotlib and Seaborn for plotting/visualizations 

**Communication**

The results and code are in this repo, along with the [final slides](https://github.com/zoel321/lr-tripadvisor/blob/master/Metis%20-%20Linear%20Regression_%20Predicting%20Tripadvisor%20Ratings.pdf):
- [Web scraping](https://github.com/zoel321/lr-tripadvisor/blob/master/tripadvisor-scraping.ipynb)
- [Cleaning](https://github.com/zoel321/lr-tripadvisor/blob/master/Tripadvisor%20-%20Data%20cleaning%20.ipynb)
- [Baseline model/MVP](https://github.com/zoel321/lr-tripadvisor/blob/master/Tripadvisor%20Regression%20-%20Baseline.ipynb)
- [Modeling](https://github.com/zoel321/lr-tripadvisor/blob/master/Tripadvisor%20Regression-full.ipynb)





