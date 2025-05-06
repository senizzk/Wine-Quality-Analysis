🍷 Wine Quality Analysis
This project analyzes the physicochemical properties of red wines to identify the key factors that influence quality ratings. Using exploratory data analysis and machine learning models, we aim to both predict wine quality and recommend feature ranges that characterize high-quality wines.

📌 Objective
The goal of this project is to:

Identify the key factors that contribute to high wine quality ratings

Provide data-driven recommendations for optimal feature ranges

Build and evaluate machine learning models to predict wine quality using classification techniques

🧹 Data Preparation Highlights
✅ Removed 240 duplicate entries to ensure data integrity

✅ Confirmed no missing values were present

✅ Treated the quality column as an ordinal variable

✅ Created both binary and multinomial classification labels to address class imbalance and support different modeling approaches

🔍 Exploratory Data Analysis
We began by exploring relationships between features and identifying early patterns:

Multicollinearity was observed among several features through scatter plots and correlation heatmaps

Positive correlations with quality:

alcohol (0.48)

sulphates (0.25)

citric acid (0.23)

Negative correlations with quality:

volatile acidity (–0.40)

density (–0.18)

These insights were further validated through box plots, which showed how these features varied across quality levels.

🤖 Modeling and Feature Selection
We used several models to determine the most important features:

Tree-based models (Decision Tree, Random Forest, Extra Trees, XGBoost)

Logistic Regression with L1 Regularization (Lasso)

Key modeling considerations:

Focused on precision and recall for high-quality wines, not just overall accuracy

Used stratified train-test splits to maintain class balance

The best performance was achieved using a binary classification (quality 3–5 = low, 6–8 = high)

⚠️ Challenges Encountered
Multicollinearity: Made feature interpretation difficult; resolved using models less sensitive to correlated inputs (e.g., tree-based and L1-regularized models)

Class Imbalance: Mid-range scores dominated the dataset; handled with binning and stratified sampling

✅ Final Model Performance
The Random Forest classifier using the binary binning strategy (3–5 as Low, 6–8 as High) delivered the best performance with the lowest number of false positives and false negatives.

Top 5 features identified:

Alcohol

Sulphates

Total Sulfur Dioxide

Volatile Acidity

Density

These results aligned well with the EDA findings, except for citric acid, which showed strong correlation but was not consistently selected by the models.

🧠 Conclusion
Key takeaways on feature influence:

Feature	Insight
Alcohol	Wines with ≥ 9.8% alcohol were more likely to be high quality
Sulphates	High-quality wines had sulphate levels between 0.63–1.1
Volatile Acidity	Best wines had low volatile acidity (0.26–0.62)
Density	Higher-quality wines had density below 0.9988
Total Sulfur Dioxide	No consistent trend; more data from extreme quality scores needed
