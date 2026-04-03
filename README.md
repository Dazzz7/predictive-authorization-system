# Health Insurance Auto-Approval Prediction

This project builds a machine learning model to predict whether a prior authorization request for pet healthcare services will be approved or denied, helping automate decision-making in insurance workflows.

📌 Problem Statement:
Insurance providers receive numerous prior authorization requests for services such as lab tests, vaccinations, and surgeries. Manually reviewing these requests is time-consuming and inefficient.

Aim:
Predict authorization status (Approved/Denied)
Identify key factors influencing approvals
Support automation of approval workflows

## About the project:
This project uses two datasets: Prior Authorization data and Claims data. The prior authorization dataset contains details about service requests such as pet ID, service type, submission date, provider, units, authorization status (approved/denied), auto-approval flag, and clinical reviewer. The claims dataset includes historical records like claim ID, claim type, claim date, amount paid, and provider information. Both datasets were merged using pet_id to link authorization requests with past claim history, enabling a more comprehensive view for prediction.

Data Processing & Feature Engineering:
The data was cleaned by standardizing column names, handling missing values (e.g., filling clinical_reviewer with “Not Assigned” and imputing amount_paid with the mean), and removing duplicates. Feature engineering included converting date fields into datetime format and creating new features such as days_to_claim along with submission month, day, and weekday. Categorical variables like service type and provider were encoded for model compatibility.

Exploratory Data Analysis (EDA):
EDA was performed to understand data distribution and relationships. The distribution of amount_paid showed skewness and outliers, while categorical analysis highlighted the proportion of approved versus denied cases. Correlation analysis and scatter plots helped identify relationships between numerical features and trends over time.

Model Building:
A Random Forest Classifier was implemented to predict the authorization status of requests. The model was trained using a set of engineered features, including service type, temporal attributes (submission month, day, weekday), claim amount, number of units, and provider information. The target variable, authstatus, was encoded into numerical form for model compatibility.

The dataset was split into training and testing sets using an 80-20 ratio to evaluate model performance on unseen data. Random Forest was chosen due to its robustness, ability to handle both numerical and categorical data, and effectiveness in capturing non-linear relationships.

Model Evaluation:
The model’s performance was evaluated using accuracy and a detailed classification report, which includes precision, recall, and F1-score. These metrics provide a comprehensive understanding of how well the model distinguishes between approved and denied cases.

Feature importance analysis was also conducted to interpret the model’s decision-making process. It revealed that factors such as auto-approval status, clinical reviewer assignment, provider information, and time differences between claim and submission significantly influence authorization outcomes.

 Key Insights:
The analysis highlights that historical claim behavior, provider patterns, and operational factors like reviewer assignment play a significant role in determining authorization outcomes. Time-based features, such as the gap between claim and submission, also contribute meaningfully to predictions. These insights can help insurance providers optimize their approval processes and identify opportunities for automation.
