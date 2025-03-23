# Smart-water-monitoring-systems

# Smart Water Monitoring System - Machine Learning Model  

## **Project Overview**  
Water scarcity is a major global issue, and inefficient consumption habits contribute to excessive water wastage. Traditional water meters provide only total usage data, making it difficult to optimize water consumption.  
This project aims to build a **Machine Learning model** that predicts **daily water consumption** for individual households based on historical usage patterns, household characteristics, weather conditions, and conservation behaviors.  

## **Dataset Description**  
The dataset consists of the following files:  
- `train.csv` - Contains 14,000 rows and 12 columns (including the target variable `Water_Consumption`).  
- `test.csv` - Contains 6,000 rows and 11 columns (without the `Water_Consumption` column).  
- `sample_submission.csv` - Provides a sample format for the final submission file.  

### **Columns in the Dataset**  
| Column Name                | Description |
|----------------------------|-------------|
| `Timestamp`                | Unique timestamp of an entry |
| `Residents`                | Number of people in the household |
| `Apartment Type`           | Type of apartment |
| `Temperature`              | Average temperature at that time |
| `Humidity`                 | Average humidity at that time |
| `Water_Price`              | Cost of water for that period |
| `Period_Consumption_Index` | Relative water usage for each 8-hour period |
| `Income Level`             | Income level of the household |
| `Guests`                   | Number of guests present |
| `Amenities`                | Types of amenities in the household |
| `Appliance Usage`          | Whether water appliances are in use |
| `Water_Consumption`        | (Target Variable) Amount of water consumed |

---

## **Machine Learning Approach**  
The following approach was taken to develop an accurate model:

### **1. Data Preprocessing**
- **Handled Missing Values**:  
  - Numerical columns were filled with the **mean**.  
  - Categorical columns were filled with the **mode**.  
- **Encoded Categorical Variables**:  
  - Used **Label Encoding** to convert categorical variables into numerical values.  
- **Ensured Consistency Between Train & Test Data**:  
  - Added missing columns to test data with default values.

### **2. Feature Selection & Engineering**
- Unnecessary columns like `Timestamp` were removed.  
- Applied transformation techniques to ensure data consistency.

### **3. Model Selection**
We used an **ensemble of three machine learning models** for higher accuracy:  
- **Random Forest Regressor** (Best for handling categorical & numerical data)  
- **Gradient Boosting Regressor** (Performs well on structured data)  
- **XGBoost Regressor** (Fast & optimized for tabular datasets)  

A **weighted averaging approach** was used to combine the predictions of these three models.

---

## **How to Run the Code**
### **Prerequisites**
Make sure you have the following installed:  
- Python (>= 3.8)  
- Jupyter Notebook  
- Required libraries (Install using the command below)  

```sh
pip install pandas numpy scikit-learn xgboost
