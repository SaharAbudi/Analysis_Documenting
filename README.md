# Brain Stroke Analysis
### Table of Contents
## Table of Contents
- [Project Overview](#project-overview)
- [Data Source](#data-source)
- [Tools](#tools)
- [Data Cleaning/Preparation](#data-cleaningpreparation)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Results/Findings](#resultsfindings)
  - [Decision Tree Classifier](#decision-tree-classifier)
  - [Logistic Regression](#logistic-regression)
  - [K-Nearest Neighbors (KNN)](#k-nearest-neighbors-knn)
- [Recommendations](#recommendations)
- [Limitations](#limitations)
- [References](#references)


### Project Overview 


This project focuses on predicting the likelihood of a brain stroke, a medical emergency caused by insufficient blood flow to the brain, leading to brain cell death. Recognizing individuals at risk can significantly reduce mortality and improve patient outcomes through timely interventions. The goal is to use machine learning techniques to develop predictive models based on a variety of health and demographic factors. Through this project, various algorithms were built and compared, analyzing their performance, accuracy, and ability to handle the inherent class imbalance in the data.

### Data Source

The dataset, Brain_Stroke.csv, was obtained from Kaggle. It consists of approximately 5,000 observations and 11 features, including gender, age, hypertension, heart disease, marital status, work type, residence type, average glucose level, BMI, smoking status, and stroke outcome. Data analysis showed a wide age range (0.08 to 82 years), highlighting the diversity of the sampled population. The relatively low stroke occurrence (about 5%) presented a significant challenge for model training, emphasizing the importance of dealing with imbalanced datasets.

### Tools
- Programming Language: Python
#### Libraries Used:
- pandas for data manipulation and analysis
- scikit-learn for building machine learning models and evaluating performance
- matplotlib for visualizing data distributions and decision tree structures
- Google Collab as the environment for coding and documenting the analysis process

### Data Cleaning/Preparation
The initial steps included importing the dataset and exploring its structure. Categorical features, such as "smoking status" and "ever married," were encoded into numerical values to facilitate model building. The data was split into training and testing subsets, with a 75%-25% or 80%-20% split depending on the model. Standardization was applied to numerical features, ensuring consistent scaling across variables. This process was crucial, especially for distance-based models like KNN. Moreover, additional features such as "ever_married" were engineered for enhanced model performance during the second decision tree iteration.

### Exploratory Data Analysis
- Age: Mean age was 43.42 years, with a wide spread and a standard deviation of 22.66 years. The age distribution suggested a younger population, although stroke occurrence tended to rise with age.
- Hypertension: Only 9.6% of the sample population had hypertension, highlighting a predominantly healthy group.
- Heart Disease: Around 5.5% of the individuals had a history of heart disease.
- Average Glucose Level: The mean glucose level was 105.94 mg/dL, with a substantial range from 55.12 to 271.74 mg/dL.
- BMI: The mean BMI was 28.5, suggesting that most individuals were overweight.
- Stroke Occurrence: Only 5% of the individuals suffered from a stroke, with a slightly higher incidence among males (5.2%) compared to females (4.8%).
### Correlation analysis showed:
- A moderate positive correlation between age and BMI (0.37).
- Weak to moderate positive correlations between hypertension, heart disease, average glucose level, and stroke incidence.
- Weak correlations between glucose level and BMI, hinting at a possible connection between obesity and high glucose levels.


### Results/Findings
#### Decision Tree Classifier
The initial decision tree model achieved a very high accuracy of 94.46% to 95.10%, almost perfectly classifying non-stroke cases. However, it failed to correctly identify stroke cases, highlighting a strong bias towards the negative class. Key features influencing decisions included average glucose level and smoking status. In a second iteration, by adjusting tree depth and adding "ever_married" as a feature, slight improvements were achieved, but the fundamental imbalance issue remained.


#### Logistic Regression
The logistic regression model offered a more balanced performance, achieving about 73.98% accuracy. It moderately improved stroke case detection compared to the decision tree. Nonetheless, the model still showed higher precision and recall for non-stroke cases, reflecting the challenge of predicting rare positive events.
#### K-Nearest Neighbors (KNN)
The KNN model achieved 87.66% accuracy when predicting non-stroke cases. Similar to other models, it showed significant difficulty detecting actual stroke incidents. Out of 114 actual stroke cases, only 5 were correctly identified, indicating a high false-negative rate.

### Recommendations
- Handle Class Imbalance: Apply oversampling techniques like SMOTE or undersampling methods to balance the stroke and non-stroke classes.
- Model Enhancement: Experiment with ensemble methods such as Random Forest, Gradient Boosting, or XGBoost, known for better performance on imbalanced datasets.
- Feature Engineering: Include more health metrics (e.g., cholesterol, physical activity) if available to improve predictive power.
- Threshold Adjustment: Modify decision thresholds to favor higher sensitivity towards detecting stroke cases.
- Hyperparameter Tuning: Conduct more extensive tuning of model parameters to optimize recall and precision for the minority class.

### Limitations
- Class Imbalance: With only 5% stroke cases, models are heavily skewed towards predicting the majority class, impacting the ability to detect true positives.
- Feature Set Limitations: Important risk factors such as family medical history, detailed lifestyle habits, and cholesterol levels are missing.
- Model Simplicity: The models implemented (Decision Tree, Logistic Regression, KNN) are relatively basic; more complex models could offer improved detection rates.
- Data Representativeness: The dataset might not fully represent global or broader demographic distributions.

References

[Kaggle Brain Stroke Prediction Dataset](https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset)

[Scikit-learn Documentation](https://scikit-learn.org/stable/)

[Matplotlib Documentation](https://matplotlib.org/)

