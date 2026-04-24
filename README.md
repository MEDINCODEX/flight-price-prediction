# ✈️ Flight Price Prediction Project

## 📝 Project Description
This project aims to build a Machine Learning model to predict flight ticket prices in India using a dataset containing over 300,000 records. The primary objective is to achieve high prediction accuracy with a Mean Absolute Error (MAE) of less than 15€ (approximately 1,350 Indian Rupees).

## 🎯 Objectives Achieved
- [x] Conducted rigorous Exploratory Data Analysis (EDA).
- [x] Developed a robust Preprocessing Pipeline (Encoding & Scaling).
- [x] Compared multiple Regression Models (Linear, Ridge, Random Forest).
- [x] Met the business target (MAE < 15€).
- [x] Calculated Confidence Intervals to ensure statistical reliability.

## 🛠️ Tools and Technologies
* **Language:** Python 3.x
* **Data Manipulation:** `Pandas`, `NumPy`
* **Machine Learning:** `Scikit-Learn`
* **Visualization:** `Matplotlib`, `Seaborn`
* **Model Export:** `Joblib`

## ⚙️ Data Preprocessing Strategy
To ensure optimal model performance, features were categorized and processed as follows:
1.  **Numerical Features:** `duration`, `days_left` (Processed using `StandardScaler`).
2.  **Ordinal Features:** `stops`, `class` (Processed using `OrdinalEncoder` to maintain logical ranking).
3.  **Nominal Features:** `airline`, `source_city`, `destination_city`, `departure_time`, `arrival_time` (Processed using `OneHotEncoder`).

## 📊 Model Comparison & Results
We tested various models to find the best fit for the data:

| Model | MAE (INR) | RMSE (INR) | R² Score |
| :--- | :--- | :--- | :--- |
| **Dummy Regressor** | 19,768 | 22,704 | 0.00 |
| **Linear Regression** | 4,500 | 6,814 | 0.91 |
| **Ridge Regression** | 4,500 | 6,814 | 0.91 |
| **Random Forest** | **1,081** | **2,798** | **0.985** |

> **Conclusion:** The **Random Forest Regressor** is the final choice, achieving an error of **1,081 INR (~12€)**, which successfully outperforms the required target of 15€.

## 📈 Reliability & Confidence Interval
With a **95% confidence level**, the average error (MAE) of the model remains between **1,061** and **1,102** INR. This proves that the model is statistically stable and highly reliable for future predictions.

## 📁 Project Structure
* `Clean_Dataset.csv`: The raw dataset.
* `Flight_Price_Analysis.ipynb`: Full Jupyter Notebook with code and explanations.
* `flight_price_predictor_model.joblib`: The exported final Pipeline (Preprocessor + Model).

## 🚀 How to Use the Model
You can load the saved pipeline and start predicting immediately:
```python
import joblib

# Load the full pipeline
model = joblib.load('flight_price_predictor_model.joblib')

# Predict on new raw data (no manual preprocessing needed)
# predictions = model.predict(new_data)
👥 Contributors
Project Lead: [MARRA Mohamed/Data Eater]

Developed as part of a professional Data Science & Machine Learning training.

---

### Final Project Insights (English):
1.  **Top Predictor:** The flight `class` (Business vs. Economy) was the most significant factor influencing price.
2.  **Time Sensitivity:** The `days_left` feature showed a strong correlation, where prices spike significantly as the departure date approaches.
3.  **Pipeline Efficiency:** By exporting a `Pipeline` instead of just a model, we ensured that all future data will be scaled and encoded automatically, preventing "Broken Features" errors during deployment.

**Congratulations on finishing this professional project! You are now ready to present it.**