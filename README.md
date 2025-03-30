# Smart Water Monitoring System

## Project Overview
This project aims to develop a Machine Learning model to predict daily water consumption for individual households. The model utilizes historical water usage data, household characteristics, weather conditions, and conservation behaviors to generate predictions.

## Approach
1. **Data Preprocessing**  
   - Converted the `Timestamp` column to datetime format and extracted useful features such as Hour, Day, and Month.  
   - Categorical features (`Apartment_Type`, `Income_Level`, `Amenities`) were treated as strings and one-hot encoded.
   - Numerical features were standardized using `StandardScaler`.
   - Missing values were handled by filling numerical columns with median values and categorical columns with "Unknown".

2. **Feature Engineering**  
   - Extracted time-based features from `Timestamp`.
   - Normalized numerical data to improve model performance.
   - Encoded categorical features to ensure compatibility with the model.

3. **Model Selection & Training**  
   - Chose `RandomForestRegressor` as the machine learning model.
   - Used a `Pipeline` with a `ColumnTransformer` for preprocessing.
   - Split data into training and validation sets (80-20 split).
   - Evaluated performance using RMSE and score function:  
     `score = max(0, 100 - np.sqrt(mean_squared_error(actual, predicted)))`

## Tools & Libraries Used
- Python  
- Pandas (for data manipulation)  
- NumPy (for numerical computations)  
- Scikit-learn (for machine learning pipeline and model training)  

## Submission
The final submission file `submission.csv` contains:
- `Timestamp`: Original formatted timestamp (DD/MM/YYYY HH)
- `Water_Consumption`: Predicted water usage for the given period.

## Running the Code
1. Install dependencies:  
   ```bash
   pip install pandas numpy scikit-learn
   ```
2. Run the Python script:  
   ```bash
   python smart_water_monitoring.py
   ```
3. The `submission.csv` file will be generated in the root directory.

## Folder Structure
```
Smart_Water_Monitoring/
│── dataset/
│   ├── train.csv
│   ├── test.csv
│── smart_water_monitoring.py
│── submission.csv
│── README.md
```

