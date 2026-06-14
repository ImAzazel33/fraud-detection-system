# Fraud Detection Analysis

## Project Overview

This project focuses on detecting fraudulent transactions using a dataset of financial transactions. The goal is to build models that accurately classify transactions as fraudulent or non-fraudulent based on several features. A range of classification algorithms are employed, and the performance of the models is evaluated through metrics such as AUC-ROC, precision, and recall.

## Table of Contents

- [Project Overview](#project-overview)
- [Data Cleaning and Preprocessing](#data-cleaning-and-preprocessing)
- [Feature Engineering](#feature-engineering)
- [Modeling](#modeling)
- [Results](#results)
- [Technologies Used](#technologies-used)
- [How to Run](#how-to-run)
- [Contributing](#contributing)
- [Contact](#contact)

## Data Cleaning and Preprocessing

1. **Missing Values**: The dataset was checked for any missing values. There were no missing values, so no imputation was required.
   
2. **Outlier Detection**: Outliers in the `amount` column were detected using the IQR method. Although outliers were identified, they were not removed since they can be crucial in fraud detection.

3. **Multicollinearity**: Multicollinearity was checked using the Variance Inflation Factor (VIF). High collinearity was addressed by creating new features such as `Actual_amount_orig` and `Actual_amount_dest`.

4. **Encoding**: Categorical data such as the `type` column was encoded using label encoding, while features like `nameOrig` and `nameDest` were excluded to avoid leakage.

## Feature Engineering

Feature engineering was performed to derive useful attributes from the existing dataset. New features such as:
- **Actual_amount_orig**: The difference between `oldbalanceOrg` and `newbalanceOrig`.
- **Actual_amount_dest**: The difference between `oldbalanceDest` and `newbalanceDest`.
  
These features were designed to enhance the predictive power of the model while reducing multicollinearity.

## Modeling

Multiple models were built to predict fraud, including:

1. **Decision Tree Classifier**: 
   - A simple decision tree was used as a baseline model. The tree model was able to capture relationships between features but showed limitations in performance.

2. **Random Forest Classifier**:
   - A Random Forest classifier was implemented as the primary model. It provided better generalization by combining multiple decision trees and reducing variance.

3. **Handling Imbalanced Data**: The Synthetic Minority Oversampling Technique (SMOTE) was applied to deal with class imbalance, ensuring the model could effectively detect fraud despite it being a minority class.

## Results

The results from the models include:

1. **Decision Tree Classifier**:
   - Accuracy: 97.24%
   - AUC-ROC: 0.97

2. **Random Forest Classifier**:
   - Accuracy: 97.33%
   - AUC-ROC: 0.97

**Key Features**: Feature importance analysis revealed that `Actual_amount_orig`, `Actual_amount_dest`, and `step` were the most important factors in predicting fraudulent transactions.

## Technologies Used

- **Python**: For data manipulation and modeling.
- **Pandas**: For data cleaning and feature engineering.
- **Scikit-learn**: For model building, evaluation, and SMOTE implementation.
- **Matplotlib & Seaborn**: For data visualization and model performance analysis.
- **Jupyter Notebook**: For running the analysis and visualizing results.

## How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/AmaanP314/fraud-detection-system.git
   cd fraud-detection-system
2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
3. Run the Jupyter notebook to perform the analysis:
    ```bash
   jupyter notebook fraud_detection.ipynb

## Contributing

Contributions are welcome! Feel free to fork the repository and submit a pull request with any suggestions or improvements.

## Contact

Amaan Poonawala - [GitHub](https://github.com/AmaanP314) | [LinkedIn](https://www.linkedin.com/in/amaan-poonawala/)

Feel free to reach out for any questions or feedback.




   
