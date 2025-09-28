# Real Airbnb Price Prediction (Los Angeles)
This project is about predicting the price of Airbnb listings in Los Angeles using machine learning. The idea is to take structured information about each listing (like number of bedrooms, bathrooms, location, etc.) and train a model that can estimate the price.

##Dataset
The dataset comes from Airbnb’s LA listings. It has lots of columns:

Numbers like latitude, longitude, accommodates, bathrooms, bedrooms, beds, review_scores_rating, etc.

Categories like room_type and property_type.

Text like name and description (we didn’t use these yet).

##Data Cleaning

###Target (Price):

-Prices were messy (some listings were $40,000+ per night).

-removed rows above the 99th percentile to get rid of extreme outliers.

###Feature Selection:

-Dropped text/unstructured columns like name and description.

-Focused on numerical and categorical data.

###Encoding Categorical Data:

-Converted room_type, property_type, etc. into numerical form using one-hot encoding.

###Train/Test Split:

-80% of the data for training, 20% for testing.

-Training set: 28,839 rows × 117 features.

-Test set: 7,210 rows × 117 features.

##Model

XGBoost, a popular gradient boosting model for structured/tabular data.

###Main settings:

500 trees

learning rate = 0.05

max depth = 8

##Results

On the test set:

MAE (Mean Absolute Error): ~69

RMSE (Root Mean Squared Error): ~142

R² (Explained Variance): ~0.75

###In plain words: The model’s predictions are usually within about $70 of the real Airbnb price, and it explains about 75% of the variation in prices.

##What Could Be Improved

Using the unstructured text columns (description, name) with NLP features.

Trying CatBoost or LightGBM (they handle categorical data better).

Tune hyperparameters to push accuracy higher.

#Takeaway

started with messy Airbnb data, cleaned it, encoded it, and trained an XGBoost model. The results are already pretty good (R² ≈ 0.75), which makes this a solid starting point for more advanced feature engineering.
