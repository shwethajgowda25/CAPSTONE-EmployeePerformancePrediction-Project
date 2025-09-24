# **AIML-Powered Employee Performance Analytics**

<img width="1024" height="1024" alt="EmployeePerformancePrediction_Image" src="https://github.com/user-attachments/assets/f4fc0853-868f-49e8-87bc-b58a6d4b1bd4" />

# **📊 Exploratory Data Analysis (EDA) Report**
**1. Data Overview and Structure**
The dataset contains employee performance data from INX Future Inc. It has 1200 rows and 28 columns, with a mix of numerical and categorical variables.
**Numerical Columns**: Age, DistanceFromHome, EmpHourlyRate, etc.
**Categorical Columns**: Gender, EmpDepartment, EmpJobRole, etc.
The target variable for prediction is **PerformanceRating**.

**2. Distribution of Performance Ratings**
The primary goal is to understand what drives employee performance. The distribution of our target variable, PerformanceRating, shows the following breakdown:
**2 - Good**: This is the most common rating.
**3 - Excellent**: The second most common rating.
**4 - Outstanding**: The least common rating, but still a significant group.
This is an imbalanced dataset, which is a key factor to consider for any future machine learning model.

**3. Relationship Between Department and Performance**
A countplot shows the distribution of performance ratings across different departments.
**R&D Department**: This department has a high number of employees with an Excellent rating.
**Sales Department**: This department has a high number of employees with a Good rating, followed by an Excellent rating.
**Human Resources**: Has a small number of employees overall, but a good mix of performance ratings.
**Development**: Shows a strong presence of Excellent and Good ratings.

**4. Relationship Between Job Role and Performance**
The job role a person holds can be a significant indicator of their performance.
**Sales Executive**: This role has the largest number of employees and shows a broad distribution of Good, Excellent, and Outstanding ratings.
**Developer**: Similar to Sales, this role also has a high number of employees with a diverse range of performance ratings.
**Manager**: This group has a notable number of employees with Excellent and Outstanding ratings.
**Data Scientist:** This is a small group, but it shows a good mix of Excellent and Outstanding performers.

**5. Total Work Experience and Performance**
The relationship between work experience and performance is crucial for understanding career progression.
Employees with Outstanding and Excellent ratings generally have a higher median total work experience compared to those with Good ratings.

**6. Experience at the Company and Performance**
This visualization focuses on how long an employee has been with the company.
Employees with higher performance ratings (Excellent and Outstanding) tend to have more years of experience at the company. This suggests that longer tenure may correlate with better performance, possibly due to gaining institutional knowledge and career growth.

**7. Data Preprocessing for AIML**
Before training a machine learning model, the data needs to be preprocessed.
**Dropping EmpNumber**: The EmpNumber column is a unique identifier and provides no predictive value, so it is dropped.
**Label Encoding**: Categorical features such as Gender, EmpDepartment, and EmpJobRole are converted into numerical representations using LabelEncoder. This is a necessary step as most machine learning algorithms only work with numerical data.
**Data Splitting**: The dataset is split into training (80%) and testing (20%) sets. This division is essential for training a model on one portion of the data and evaluating its performance on unseen data, which is a standard practice in machine learning.

# **Model Performance Report: Random Forest Classifier Baseline**
Based on the baseline model training code and the results from the Jupyter notebook, here is a comprehensive analysis and model performance report.

**1. Model Performance Metrics**
A machine learning model's performance is measured by key metrics that indicate its predictive power and reliability.
**Accuracy**: The model's accuracy, which is the overall proportion of correctly predicted performance ratings, is a strong indicator of its effectiveness.
**Precision, Recall, and F1-Score**: These metrics provide a more detailed breakdown of performance for each rating category. A high F1-score across all categories (Good, Excellent, Outstanding) would indicate that the model is well-balanced and performs consistently.
**Business Implications**: The model's high accuracy suggests it's a reliable tool for predicting employee performance. This allows management to proactively identify employees who may be at risk of lower performance and offer targeted support or training.

**2. Feature Importance Analysis**
The most valuable insight from Random Forest model is its ability to identify which features have the most influence on an employee's performance rating. The results from our model reveal the following:

<img width="1368" height="845" alt="Screenshot 2025-09-24 113731" src="https://github.com/user-attachments/assets/db67e684-20ad-451f-ac6d-d921b0321d63" />

# **📈 Advanced Metrics and Analysis Report**
**1. Attrition vs. Performance**
A critical metric for any organization is the relationship between performance and employee turnover (attrition). An analysis of the Attrition and PerformanceRating columns reveals important insights:
**Low Attrition Among High Performers**: Employees with an "Outstanding" performance rating (4.0) show a significantly lower attrition rate compared to other groups.
**Higher Attrition Among Good Performers**: A notable number of employees with a "Good" performance rating (2.0) have left the company. This could indicate that employees with average performance might be more likely to seek new opportunities elsewhere.
**Actionable Insight**: The company should investigate why good performers are leaving and implement strategies to improve retention for this group, as they form the largest portion of the workforce.

**2. Last Salary Hike & Performance**
The EmpLastSalaryHikePercent variable can reveal if compensation is a significant driver of performance.
**Positive Correlation**: There is a clear positive correlation between a higher EmpLastSalaryHikePercent and a higher PerformanceRating.
**Key Findings**:
Employees with an Outstanding rating received a higher average salary hike percentage in their last review.
This metric can be a powerful predictor of performance, suggesting that rewarding employees financially for their efforts leads to better results and a higher likelihood of achieving top ratings.

**3. Job Satisfaction & Performance**
This analysis examines how different facets of employee satisfaction correlate with performance. It provides a more holistic view beyond just direct work output.
Environment Satisfaction: Employees with a higher EmpEnvironmentSatisfaction score are more likely to have Excellent or Outstanding ratings. This suggests that a positive work environment is a key factor in high performance.
**Job Involvement**: The EmpJobInvolvement metric shows a strong relationship with performance. High performers (Excellent and Outstanding) report a higher level of job involvement, which makes sense as engaged employees are more likely to excel.
**Relationship Satisfaction**: EmpRelationshipSatisfaction also shows a positive correlation with performance. Good relationships with colleagues and managers can create a supportive atmosphere that fosters high-level performance.
**Work-Life Balance**: The EmpWorkLifeBalance metric, while important, shows a less direct relationship with performance ratings compared to other satisfaction metrics. This indicates that while it's a valuable factor for employee well-being, it may not be a primary driver of performance in this dataset.

**4. Statistical Summary of Key Numerical Metrics**
A summary of key numerical columns provides a quantitative understanding of the data's central tendencies and spread, segmented by performance rating.

<img width="1754" height="322" alt="image" src="https://github.com/user-attachments/assets/da984b6c-3e8f-4564-ab6b-8bef12ed479c" />

# **Key Findings**: 
**The data shows a clear trend**: 
Employees with higher performance ratings have, on average, more total work experience, longer tenure at the company, and received higher salary increases. The EmpHourlyRate remains relatively consistent across all groups, suggesting it is not a strong indicator of performance.

# **Business Implications & Next Steps**
The insights from this baseline model are valuable for making data-driven decisions:
**Reward and Recognition**: The top features confirm that financial incentives and a supportive work environment are crucial for driving and maintaining high performance. The company should ensure these are key components of their employee management strategy.
**Career Development**: The importance of **YearsSinceLastPromotion** and **YearsInCurrentRole** suggests that establishing clear career paths and providing opportunities for advancement can directly improve employee performance.
**Proactive Management**: The model can be used to identify employees who may be at risk of underperforming. By analyzing their attributes and comparing them to the top features, managers can intervene early with targeted support.

# **Next Steps for the Project:**
**Hyperparameter Tuning**: Refine the Random Forest model by tuning its hyperparameters (n_estimators, max_depth, etc.) to improve its performance.
**Feature Engineering**: Create new features from existing data that might better capture the relationships with performance (e.g., a ratio of salary hike to years of experience).
**Alternative Models**: Test other machine learning models like Gradient Boosting or SVM classifier to see if they can achieve better performance.
