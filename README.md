# Movie Booking Demand Prediction (EDA + XGBoost)

This repository contains a complete machine learning workflow implemented in a Jupyter Notebook for predicting movie booking demand using multiple real-world datasets.  
The project covers **data loading, exploratory data analysis (EDA), feature engineering, preprocessing, model training using XGBoost, and submission generation**.

---

## 📂 Datasets Used

The project works with multiple related datasets:

- **booknow_visits** – User visit-level data
- **booknow_booking** – Booking transactions from BookNow
- **cinePOS_booking** – Booking transactions from CinePOS
- **booknow_theaters** – Theater metadata (BookNow)
- **cinePOS_theaters** – Theater metadata (CinePOS)
- **movie_theater_id_relation** – Mapping between BookNow and CinePOS theater IDs
- **date_info** – Date-level features (weekday, holiday, etc.)
- **sample_submission** – Submission format

All datasets are loaded using `pandas.read_csv()` and validated via shape checks.

---

## 🔍 Exploratory Data Analysis (EDA)

EDA is performed separately on key datasets to:

- Understand schema and feature meanings
- Inspect data types and missing values
- Check record counts and overlaps
- Identify potential joins and mappings

Basic statistics and structure checks ensure the data is ready for merging and feature creation.

---

## 🔗 Data Integration & Merging

Key merge operations include:

- Mapping **BookNow theaters** to **CinePOS theaters** using the relation map
- Combining booking data from multiple sources
- Joining **date-level features** to transactional data
- Aligning training and test data structures

Care is taken to maintain consistency across train and test sets.

---

## 🛠 Feature Engineering

Feature engineering focuses on improving predictive signal by:

- Separating **categorical** and **numerical** features
- Encoding categorical variables
- Aggregating booking and visit information
- Preparing features compatible with tree-based models

Feature lists are explicitly defined and reused to ensure alignment.

---

## 🔄 Data Preprocessing

Preprocessing steps include:

- Handling missing values
- Ensuring identical feature columns in train and test data
- Type consistency across merged datasets
- Preparing final matrices for model input

No data leakage is introduced between train and test sets.

---

## ✂️ Train–Validation Split

- The dataset is split into training and validation sets
- Validation data is used for unbiased performance evaluation
- Random state is fixed for reproducibility

---

## 🤖 Model Training

### Model Used
- **XGBoost Regressor (`XGBRegressor`)**

### Why XGBoost?
- Handles non-linear relationships well
- Robust to feature scaling
- Strong performance on tabular data

### Training Details
- Model is trained on engineered features
- Hyperparameters are explicitly defined
- Validation predictions are generated for evaluation

The final trained model is stored and reused for test predictions.

---

## 📈 Evaluation

Model performance is evaluated on the validation set using regression-appropriate metrics.  
Predictions are visually and numerically inspected to ensure reasonable behavior.

---

## 📤 Submission Generation

- Predictions are generated on the test dataset
- Results are inserted into the `sample_submission` format
- Final submission file is prepared and exported

This ensures compatibility with the competition / evaluation system.

---

## 🧰 Libraries & Tools Used

- Python
- Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- XGBoost
