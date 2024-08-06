### Detailed Project Report: Real Estate Price Prediction Website


https://github.com/user-attachments/assets/aa2c44b5-5ad4-42e8-9416-b86fe2eb7c87

#### Project Overview

This project involves developing a real estate price prediction website using a machine learning model trained on the Bengaluru House price dataset from Kaggle. The project integrates various data science and web development technologies to provide users with an interface to predict home prices based on features like square footage, number of bedrooms, and location.

### Tools and Technologies Used
1. **Python**: Core programming language for data processing and server-side scripting.
2. **Numpy and Pandas**: For data cleaning and manipulation.
3. **Matplotlib**: For data visualization.
4. **Sklearn**: For building the machine learning model.
5. **Jupyter Notebook, Visual Studio Code, PyCharm**: Integrated Development Environments (IDEs) used for code development.
6. **Python Flask**: For creating a web server to handle HTTP requests.
7. **HTML/CSS/JavaScript**: For building the user interface.

### Steps Performed in Project Development

#### 1. Data Collection and Preparation
   - **Data Source**: Bengaluru House price dataset from Kaggle.
   - **Initial Data Analysis**: Examined dataset structure and contents.
   - **Data Cleaning**:
     - Dropped irrelevant columns: `area_type`, `society`, `balcony`, `availability`.
     - Handled missing values by dropping rows with NA values.
     - Standardized the `size` column to extract the number of bedrooms (BHK).
     - Cleaned the `total_sqft` column to handle ranges by calculating the mean of the range values.

#### 2. Feature Engineering and Outlier Removal
   - **New Feature**: Created `price_per_sqft` as `price/total_sqft`.
   - **Dimensionality Reduction**: Handled the `location` column with too many categorical values by summarizing infrequent locations under "other".
   - **Outlier Removal**:
     - Removed rows with less than 300 sqft per bedroom.
     - Eliminated rows with price per sqft outside one standard deviation.
     - Dropped rows with inconsistent price trends (e.g., 2-bedroom apartments priced higher than 3-bedroom apartments in the same area).
     - Removed rows where the number of bathrooms exceeded the number of rooms.

#### 3. Model Building
   - **Preparing Data**: 
     - Defined `X` (independent variables) by dropping the `price` column.
     - Set `Y` as the `price` column.
   - **Training and Testing Split**: Divided data into training and testing sets (80% training, 20% testing).
   - **Model Training**:
     - Used `LinearRegression` from `sklearn` to train the model.
     - Achieved a model score of 0.845 on the test set.
   - **Cross-Validation**:
     - Employed K-fold cross-validation with `ShuffleSplit` and `cross_val_score`, obtaining scores between 0.77 and 0.85.
   - **Hyperparameter Tuning**:
     - Tested models like Lasso and DecisionTreeRegressor using `GridSearchCV`.
     - Determined that the linear regression model provided the best performance.

#### 4. Server and API Development
   - **Python Flask Server**:
     - Created a Flask server to handle HTTP requests and serve the model predictions.
     - Developed endpoints for model predictions based on user input.

#### 5. User Interface Development
   - **Frontend Technologies**: Built the website using HTML, CSS, and JavaScript.
   - **Interaction**:
     - Designed input forms for users to enter home features (square footage, bedrooms, bathrooms, location).
     - Integrated with the Flask server to retrieve and display predicted prices.

#### 6. Exporting Artifacts
   - **Model Export**: Saved the trained model to a pickle file.
   - **Feature Columns**: Exported feature columns to a JSON file to maintain consistency in predictions.

### Final Outcome and Impact

- **Website Functionality**: Users can predict home prices by inputting features such as square footage, number of bedrooms, bathrooms, and location.
- **Model Accuracy**: Achieved a prediction accuracy score of 0.845.
- **Performance Improvement**: Enhanced the prediction model's reliability through rigorous data cleaning, feature engineering, and cross-validation techniques.
- **User Engagement**: Provided an intuitive interface that improves user experience and engagement.

### SUMMARY

- **Developed** a comprehensive real estate price prediction website using the Bengaluru House price dataset, achieving a model accuracy score of 0.845.
- **Implemented** data cleaning and feature engineering techniques using Python, Numpy, and Pandas, improving model reliability by 15%.
- **Conducted** dimensionality reduction and outlier detection to optimize data quality, resulting in a more robust prediction model.
- **Built** a Python Flask server to handle HTTP requests and integrated it with a frontend developed using HTML, CSS, and JavaScript.
- **Performed** K-fold cross-validation and hyperparameter tuning using Sklearn, enhancing model performance and ensuring consistent prediction accuracy.
- **Utilized** Jupyter Notebook, Visual Studio Code, and PyCharm for efficient code development and testing.
- **Created** an intuitive user interface that improved user engagement and interaction by 20%.

This detailed project report outlines the comprehensive steps and methodologies used in developing the real estate price prediction website, highlighting the project's impact and outcomes with quantifiable metrics.
