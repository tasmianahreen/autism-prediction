# 🧠 Adult Autism Prediction
This project develops and evaluates machine learning models to predict autism in adults using survey and demographic data. The goal is to assist early screening and awareness through reliable, automated predictions.

I've used a structured dataset of 800 records, containing key features such as:

* AQ-10 screening scores (A1–A10)
* Demographic information (age, gender, ethnicity, country of residence)
* Medical history (e.g., jaundice at birth, family autism history)
* The target variable is the Class/ASD label, indicating whether an individual is likely to be autistic.

# 🔧 Workflow
1️⃣ Data Preprocessing
* Cleaning: Fixed typos, dropped redundant columns (like ID and single-value fields), and standardized country names.
* Handling Missing Values: Replaced missing entries in ethnicity and relation with a default category ("Others").
* Feature Encoding: Applied label encoding to convert categorical variables (e.g., gender, autism, relation) into numerical format.
* Class Imbalance: The dataset was imbalanced (639 non-ASD vs. 161 ASD cases). We used SMOTE (Synthetic Minority Over-sampling Technique) to balance the classes during training.

2️⃣ Exploratory Data Analysis
* Visualized distributions of numerical features (age, AQ scores).
* Analyzed class balance and outliers.
* Created count plots for categorical variables to understand their spread.

3️⃣ Model Training
Trained and compared the following models:

* Decision Tree: Simple and interpretable baseline.
* Random Forest: Ensemble of decision trees to improve accuracy and reduce overfitting.
* XGBoost: Gradient boosting framework offering strong performance.

4️⃣ Hyperparameter Tuning
Used RandomizedSearchCV for each model to find the optimal hyperparameters, using 5-fold cross-validation for reliable performance estimates.

5️⃣ Model Evaluation
Metrics:

* Accuracy
* Confusion Matrix
* Cross-Validation Score

📈 Results:

* XGBoost achieved the highest accuracy of ~92%.
* Random Forest and Decision Tree followed with slightly lower performance, but the Decision Tree provided the most interpretability.

🔑 Key Takeaways
* Ensemble methods (Random Forest, XGBoost) are highly effective for tabular data with both categorical and numerical features.
* Addressing class imbalance was crucial for avoiding biased predictions.
* Top predictive features included AQ-10 survey scores and specific demographic variables.

📂 Project Structure
* autism_prediction.ipynb: Main notebook with full analysis, model training, and results.

* encoders.pkl: Saved encoders for future use.

(Planned) best_model.pkl: To save the trained model for deployment.

✅ Requirements
* Python (latest version)
* scikit-learn
* XGBoost
* pandas, numpy, matplotlib, seaborn
