🏠 California Housing Price Prediction

This project builds a Machine Learning pipeline using Scikit-Learn to predict median_house_value from housing data.

It includes:

✅ Data preprocessing pipeline

✅ Stratified train-test split

✅ Random Forest Regressor model

✅ Model + Pipeline saving using joblib

✅ Inference on new input data

📂 Project Structure
│── housing2.csv        # Training dataset
│── input.csv           # New data for prediction
│── output.csv          # Predictions saved here
│── model.pkl           # Saved trained model
│── pipeline.pkl        # Saved preprocessing pipeline
│── main.py             # Main script (your code)
│── README.md           # Project documentation

⚙️ How It Works
🔹 1. Training Phase (Runs Only If model.pkl Does Not Exist)

Loads dataset from housing2.csv

Creates income categories using median_income

Performs Stratified Shuffle Split

Separates:

Features

Labels (median_house_value)

Builds preprocessing pipeline:

Numerical features:

Median imputation

Standard scaling

Categorical feature:

One-hot encoding (ocean_proximity)

Trains a RandomForestRegressor

Saves:

model.pkl

pipeline.pkl

🔹 2. Inference Phase (Runs If model.pkl Exists)

Loads saved model and pipeline

Reads new data from input.csv

Applies preprocessing pipeline

Generates predictions

Saves predictions to output.csv

🧠 Machine Learning Details
🔹 Model Used

RandomForestRegressor

Why Random Forest?

Handles non-linearity well

Works great with mixed feature types

Reduces overfitting using ensemble learning

🔹 Preprocessing Steps
Feature Type	Processing
Numerical	Median Imputation + StandardScaler
Categorical	OneHotEncoder (handle_unknown="ignore")
📦 Requirements

Install dependencies:

pip install pandas numpy scikit-learn joblib

▶️ How To Run
Step 1: Training

Ensure:

housing2.csv


exists in the directory.

Run:

python main.py


This will create:

model.pkl
pipeline.pkl

Step 2: Prediction

Create input.csv (same feature columns except median_house_value)

Run the script again:

python main.py


Predictions will be saved in:

output.csv

📝 Important Notes

input.csv must have exact same feature columns as training data (except target column).

ocean_proximity must be included.

If new unseen categories appear → OneHotEncoder safely ignores them.

🔁 Pipeline Design
Raw Data
   ↓
ColumnTransformer
   ├── Numerical Pipeline
   │     ├── Median Imputer
   │     └── StandardScaler
   │
   └── Categorical Pipeline
         └── OneHotEncoder
   ↓
RandomForestRegressor
   ↓
Prediction

🚀 Future Improvements

Add hyperparameter tuning (GridSearchCV)

Add model evaluation metrics (RMSE, MAE)

Add logging instead of print statements

Add Docker support

Convert to REST API using Flask / FastAPI

👨‍💻 Author

Prathmesh Nirmal
Machine Learning Project