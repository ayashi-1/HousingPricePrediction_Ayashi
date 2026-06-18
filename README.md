# HousingPricePrediction_Ayashi
Internship Week 1 Project - AI Driven House Price Prediction using ML
# Summary of the Notebook

This notebook performs an AI-driven house pricing system. The steps are as follows:

1.  **Data Loading**: The dataset from "/content/NY-House-Dataset (1).csv" is loaded into a pandas DataFrame.
2.  **Data Cleaning and Processing**: Missing values and duplicate rows are checked and handled.
3.  **Exploratory Data Analysis**: Various visualizations are created to understand the distribution of key features, their relationship with price, price distribution on a map, price distribution across localities and sublocalities, relationships between numerical features using a pair plot, and the distribution of brokers.
4.  **Feature Engineering**: New features like 'BEDS\_BATHS\_RATIO', 'TOTAL\_ROOMS', and 'IS\_DOUGLAS\_ELLIMAN' are created. Logarithmic transformations are applied to 'PRICE' and 'PROPERTYSQFT'.
5.  **Model Training and Evaluation**: Several machine learning models (Linear Regression, Neural Network, LightGBM, XGBoost, and Random Forest) are trained to predict house prices. The models are evaluated using metrics such as MAE, MSE, RMSE, and R2 score. An averaging ensemble model is also created and evaluated. Based on the evaluation metrics, **LightGBM**, **XGBoost**, and **Random Forest** were the top 3 performing models.Based on the evaluation metrics, LightGBM was the best performing individual model.
6.  **Model Comparison**: The evaluation metrics of all models are displayed and visualized. The first 10 actual vs. predicted prices for all models are shown, and actual vs. predicted prices are visualized for each model. The evaluation metrics and predictions of the top 3 models are also displayed.

# Results and Discussion

1. **Most Influential Features**: Property square footage and geolocation (latitude and longitude) were the strongest drivers of house price, followed by number of bedrooms and bathrooms. Location consistently overshadowed structural features — properties in prime Manhattan areas commanded prices no room count alone could justify.

2. **Model Accuracy**: LightGBM was the best performing model with an R² of around 0.60, meaning it explained roughly 60% of the variation in house prices. For a dataset as noisy and complex as real estate, this is a solid and meaningful result.

3. **What Surprised Me**: The number of bedrooms mattered far less than expected on its own. Square footage and location coordinates consistently outweighed it across all five models. The extreme price skewness was also striking — a small cluster of ultra-luxury properties skewed the entire distribution so heavily that log transformation was necessary before training.

4. **Business Recommendation**: Real estate platforms should invest in location-aware pricing models rather than relying on room counts or manual comparables. A well-tuned LightGBM or XGBoost model, updated periodically with fresh listings data, would serve as a far more reliable and scalable valuation tool.
