# Bangalore House Price Prediction 🏠

A machine learning project to predict residential property prices in Bangalore using Linear Regression.

## 📂 Dataset
- **Source:** Bengaluru House Data (CSV)
- **Features used:** Location, Total Sqft, Size (BHK), Bath, Price

## 🛠️ Tech Stack
Python, Pandas, NumPy, Scikit-learn, Seaborn, Matplotlib

## 🔄 Project Pipeline

### 1. Data Cleaning
- Dropped irrelevant columns: `area_type`, `availability`, `society`, `balcony`
- Handled missing values using `dropna()`
- Cleaned `size` column — removed "BHK", "Bedroom", "RK" labels
- Cleaned `total_sqft` — removed unit labels (Sq. Meter, Acres, etc.)
- Converted range values (e.g. "1200-1500") to their average

### 2. Encoding
- Grouped rare locations (< 10 occurrences) as `"others"`
- Applied One-Hot Encoding on `location` using `sklearn.OneHotEncoder`

### 3. Outlier Treatment
- Used **IQR-based clipping** on `total_sqft`, `bath`, `price`, and `size`

### 4. Model Training
- Split data: 75% train, 25% test (`random_state=42`)
- Standardized features using `StandardScaler`
- Trained a **Linear Regression** model

### 5. Evaluation
- **5-Fold Cross Validation R²:** 0.63
- **Final Test R² Score:** 0.64

> Baseline Linear Regression model. Scope for improvement using ensemble methods like Random Forest or XGBoost.

## 📁 Files
| File | Description |
|------|-------------|
| `bengaluru_house_prediction.ipynb` | Main notebook |
| `Bengaluru_House_Data.csv` | Raw dataset |
