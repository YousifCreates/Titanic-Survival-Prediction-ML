# 🛳️ Titanic Survival Prediction using Support Vector Classifier (SVC)

This project applies **Support Vector Machines (SVM)** for predicting survival on the Titanic dataset.  
The Titanic dataset is one of the most famous machine learning problems, making it ideal for practicing classification techniques.  

## 📌 Project Overview
- **Goal:** Predict whether a passenger survived or not based on features such as class, age, sex, and fare.  
- **Algorithm Used:** Support Vector Classifier (SVC) with RBF kernel.  
- **Performance Achieved:** ~79% accuracy on the test dataset.  

## 📂 Dataset
The dataset is available on [Kaggle Titanic: Machine Learning from Disaster](https://www.kaggle.com/c/titanic).  

It contains information about passengers such as:
- Passenger class (`Pclass`)
- Name, Sex, Age
- Number of siblings/spouses aboard (`SibSp`)
- Number of parents/children aboard (`Parch`)
- Ticket, Fare, Cabin, and Embarked port
- Target variable: **Survived (0 = No, 1 = Yes)**  

## ⚙️ Steps Performed
### 1. Data Preprocessing
- Handled missing values:
  - `Age`: Filled with median grouped by `Pclass` and `Sex`.
  - `Embarked`: Filled with mode.
  - Dropped high-missing-value columns (`Cabin`, `Ticket`, `Name`, `PassengerId`).
- Performed **One-Hot Encoding** for categorical variables (`Sex`, `Embarked`).
- Applied **StandardScaler** for feature scaling.  

### 2. Exploratory Data Analysis (EDA)
- Visualized PCA (2D projection) of the dataset.  
- Plotted **Age vs Fare** scatter plot colored by survival status.  

### 3. Model Training
- Used `SVC` from scikit-learn with:
  - Kernel = **RBF**
  - `C = 1.0`
  - `gamma = 0.001`
- Split dataset into **65% training** and **35% testing**.  

### 4. Model Evaluation
- **Classification Report**:
  - Class 0 (Non-survivors): Precision 0.77, Recall 0.79, F1 = 0.78
  - Class 1 (Survivors): Precision 0.67, Recall 0.65, F1 = 0.66
- **Overall Accuracy:** ~73%  

## 📊 Results & Conclusion
- The model predicts **non-survivors more accurately than survivors**, due to slight class imbalance in the dataset.  
- Achieved **79% accuracy**, showing SVC provides reasonable performance.  
- Improvements possible through:
  - Hyperparameter tuning (`C`, `gamma`, `kernel`).
  - Feature engineering (e.g., extracting `Title` from names, family size features).
  - Trying other ML models like Random Forest, Gradient Boosting, Logistic Regression.  
1. Clone this repository:
   ```bash
   git clone https://github.com/YousifCreates/Titanic-Survival-Prediction-ML
   cd titanic-svc
