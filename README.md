# -Singapore-Resale-Flat-Prices-Prediction
This project builds a Singapore Flat price prediction. Users input details like town and area, and the app predicts the price using a pre-trained model.

Introduction : The project addresses the challenges in accurately estimating resale flat prices in the competitive Singapore market. The predictive model leverages machine learning algorithms to analyze various factors, providing users with reliable estimates for resale prices.

Key Technologies and Skills :
*Python
*Numpy
*Pandas
*Scikit-Learn
*Matplotlib
*Seaborn
*Pickle
*Streamlit

Data Preprocessing:-
Data Understanding: Before diving into modeling, it's crucial to gain a deep understanding of your dataset. Start by identifying the types of variables within it, distinguishing between continuous and categorical variables, and examining their distributions. In our dataset.

Encoding and Data Type Conversion: To prepare categorical features for modeling, we employ LabelEncoder encoding. This technique transforms categorical values into numerical representations based on their intrinsic nature and their relationship with the target variable. Additionally, it's essential to convert data types to ensure they match the requirements of our modeling process.

Skewness - Feature Scaling: Skewness is a common challenge in datasets. Identifying skewness in the data is essential, and appropriate data transformations must be applied to mitigate it. One widely-used method is the log transformation, which is particularly effective in addressing high skewness in continuous variables. This transformation helps achieve a more balanced and normally-distributed dataset, which is often a prerequisite for many machine learning algorithms.

Outliers Handling: Outliers can significantly impact model performance. We tackle outliers in our data by using the Interquartile Range (IQR) method. This method involves identifying data points that fall outside the IQR boundaries and then converting them to values that are more in line with the rest of the data. This step aids in producing a more robust and accurate model.

Exploratory Data Analysis (EDA) and Feature Engineering:

Skewness Visualization: To enhance data distribution uniformity, we visualize and correct skewness in continuous variables using Seaborn's Histplot and boxplot. By applying the Log Transformation method, we achieve improved balance and normal distribution, while ensuring data integrity.

Outlier Visualization: We identify and rectify outliers by leveraging Seaborn's Boxplot. This straightforward visualization aids in pinpointing outlier-rich features. Our chosen remedy is the Interquartile Range (IQR) method, which brings outlier data points into alignment with the rest of the dataset, bolstering its resilience.

Algorithm Selection: After thorough evaluation, Random Forest Regressor, demonstrate commendable testing accuracy. Upon checking for any overfitting issues in both training and testing, both models exhibit strong performance without overfitting concerns. I choose the Random Forest Regressor for its ability to strike a balance between interpretability and accuracy, ensuring robust performance on unseen data.
   - Hyperparameter Tuning with GridSearchCV and Cross-Validation: To fine-tune our model and mitigate overfitting, we employ GridSearchCV with cross-validation for hyperparameter tuning. This function allows us to systematically explore multiple parameter values and return the optimal set of parameters. {'max_depth': 20, 'max_features': ='log2', 'min_samples_leaf': 2, 'min_samples_split': 5}

*the workflow:

1.Import Libraries: Import necessary libraries like streamlit for building the app, pickle for loading the model, and numpy for numerical operations.
2.Load Model: Open the saved flat price prediction model (likely a machine learning model) stored in a .pkl file.
3.Define Features: Specify a list containing all the features used by the model for prediction. These features likely represent various aspects of a house.
4.Categorical Mapping: Create dictionaries that map categorical features (like town names) to numerical values the model understands. This is because models 
  typically work better with numbers.
5.App Title: Set the title of the web app displayed to the user.
6.Input Data Dictionary: Create an empty dictionary to store user input for each feature.
7.User Input Widgets: Loop through each feature:
   - If the feature is categorical (like town):
        a.Display a dropdown menu in the sidebar for users to choose a specific option (e.g., town name).
        b.Based on the chosen option, assign the corresponding numerical value (from the mapping dictionary) to the input data dictionary.
   - Otherwise (if the feature is numerical):
        a.Display a number input field in the sidebar for users to enter a value (e.g., floor area).
        b.Assign the entered value to the input data dictionary.
8.Prediction Button: Create a button in the sidebar labeled "Predict."
9.Prediction Logic: When the button is clicked:
     a.Create a NumPy array by:
         - Looping through features and extracting their corresponding values from the input data dictionary.
         - Reshaping this list of values into a single row with multiple columns (suitable for model input).
     b.Use the loaded model to predict the house price based on the user-provided input data.
10.Prediction Scaling: The model might predict on a different scale. Apply necessary transformation (likely exponential) to convert the prediction to a more 
   interpretable value (e.g., actual house price).
11.Display Result:
    - Create a subheading "Prediction Result."
    - Display a formatted string showing the predicted house price with appropriate units (e.g., Singapore Dollars) and two decimal places.

conclusion :
The conclusion of this project would involve deploying a user-friendly web application that leverages a trained machine learning model to predict resale prices for flats in Singapore. This application would empower both buyers and sellers with an estimated resale value based on various factors like location and flat type.

Additionally, the project would deliver a comprehensive report outlining the data analysis, model development, deployment process, and achieved results. This documentation would serve as a valuable resource for understanding the project's functionalities and potential for further development.

*Real time benifits of this project : The real-time benefits of this project lie in the web application's ability to provide instant estimates for resale flat prices in Singapore. Here's how it can be advantageous:

- Faster Decision Making:  For potential buyers, the app can quickly estimate a flat's value, allowing them to compare prices and make informed choices efficiently. Sellers can get a ballpark figure of their flat's worth, helping them set a competitive asking price or negotiate effectively.

- Increased Transparency:  The application can improve transparency in the resale market by offering an objective estimate based on data analysis. This can help reduce reliance on guesswork or anecdotal evidence, leading to fairer negotiations for both parties.

- Greater Accessibility:  Anyone with an internet connection can access the web application, democratizing the process of estimating resale flat prices. This empowers even first-time buyers or sellers who might not have prior experience in the market.

- Improved Market Efficiency:  By providing readily available estimates, the application can streamline the process of valuing flats. This can potentially lead to faster transactions and a more efficient overall market.

It's important to remember that the predictions are estimates, and actual market conditions can still influence final prices. However, the real-time nature of this web application offers significant advantages for those navigating the Singaporean resale flat market.

*Real time examples: While this specific project is hypothetical, there are real-time examples of similar applications used in the housing market,

1.Zillow Zestimate:  A widely used example in the US is Zillow's Zestimate. This feature on the Zillow website uses a machine learning model to generate an estimated market value for a property based on public data like location, size, and recent sales of comparable homes.  Similar to the proposed project, home buyers can use Zestimate for quick price comparisons and sellers can get a starting point for listing their property.

2.Trulia Market Value: Another US example is Trulia's Market Value feature. It provides an estimated market value for a property along with a confidence score indicating the accuracy range of the estimate. This allows users to gauge the reliability of the prediction alongside the estimated price.

These real-time examples showcase how machine learning models can be integrated into user-friendly web applications to empower users in the housing market. The Singaporean resale flat prediction project aims to achieve similar benefits for that specific market.



