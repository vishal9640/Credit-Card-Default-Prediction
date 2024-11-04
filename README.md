# Credit-Card-Default-Prediction
The primary objective of this project is to create a robust predictive model for assessing the risk of payment default among clients based on a comprehensive dataset of 30,000 individuals from Taiwan. The project aims to achieve the following specific goals:<br>
**1. Data Exploration and Preprocessing:**
Conduct an in-depth exploratory data analysis (EDA) to understand the dataset's structure, identify trends, and visualize relationships among variables.<br>
Address data quality issues, such as missing values and outliers, to ensure the integrity of the dataset.<br>
**2. Address Class Imbalance:**<br>
Analyze the extent of class imbalance within the dataset, where a minority of clients default on payments.
#Implement techniques such as resampling (oversampling the minority class or undersampling the majority class), synthetic data generation (e.g., SMOTE), or adjusting class weights to mitigate the imbalance and improve model training.
**3. Feature Engineering**:<br>
Identify and create relevant features that contribute to predicting payment defaults, leveraging the available demographic, financial, and historical payment data.<br>
Assess the importance of different features using techniques like feature selection or dimensionality reduction to enhance model performance.<br>
**4. Model Development and Evaluation**:<br>
Develop multiple machine learning models (e.g., logistic regression, decision trees, random forests, and ensemble methods) to compare their performance in predicting defaults.<br>
Evaluate model performance using appropriate metrics such as accuracy, precision, recall, F1-score, and AUC-ROC, with a focus on improving metrics relevant to the minority class.<br>
**5. Validation and Testing**:<br>
Implement cross-validation techniques to ensure the robustness and generalizability of the models.<br>
Test the final model on unseen data to validate its predictive capability and reliability in real-world scenarios.<br>
**6. Insights and Recommendations:**<br>
Provide actionable insights and recommendations for financial institutions on identifying high-risk clients, thereby aiding in credit risk management.<br>
Discuss potential implications of the findings on future lending practices and client management strategies.<br>
By achieving these objectives, the project aims to contribute valuable knowledge in the area of credit risk assessment and enhance the ability of financial institutions to make informed decisions regarding client creditworthiness.
<br>
<br>

**1. Data Characteristics:** A quick look at the dataset with info() and describe() reveals the data types, ranges, and statistical summaries (mean, median, etc.). This helps us understand the scope of the problem and identify potential issues like missing values or outliers.
<p align="center">
  <img src="https://github.com/user-attachments/assets/b14217da-c5ba-4702-9b49-e67f5f29cdcf"/></p>
  <p align="center"> Basic Statistics describing the data and quick look of dataset and their statistics </p>
<br>
<p align="left">
  <img src="https://github.com/user-attachments/assets/074f74cb-8134-4f34-98a7-139b18c6b438"/>
  <img src="https://github.com/user-attachments/assets/3541d18e-f36f-456d-9779-f9fe86ef7a54"/>
</p>
  <p align="center"> Basic info output and statistics of dataset output </p>
<br>
<br>

**2.Data Cleaning / Preprocessing:** Cleaning and preprocessing are essential steps to prepare the dataset for machine learning models:<br>
•	Handling Missing Values: Although this dataset does not have significant missing data, checking for null values ensures we don’t overlook any inconsistencies (isnull().sum()).<br>
•	Removing Duplicates: Duplicate entries, if any, are removed to avoid data leakage.<br>
•	Encoding Categorical Features:<br>
    o	Label Encoding: Converts categorical values (e.g., gender) into numeric forms for compatibility with machine learning models.<br>
•	Handling Outliers: Outliers in features like LIMIT_BAL or BILL_AMT may skew the model’s predictions. We either cap or remove such extreme values, if necessary.<br>
<p align="center">
  <img src="https://github.com/user-attachments/assets/1352ec24-48a4-48b2-ab7e-f3c06daa9bb8"/></p>
  <p align="center">Checking for Missing Values in dataset</p>
<p align="center">
  <img src="https://github.com/user-attachments/assets/b16d8137-7201-4c73-bed1-edce67a54243"/></p>
  <p align="center">Output for Missing Values in dataset </p>
<br>
<br>

**3. Data Visualization – Independent Features:** Visualization allows us to explore trends and patterns within the data, helping to uncover insights and make informed decisions:<br>
•	Target Distribution: We use a count plot to visualize the distribution of the target variable (default payment next month). This step helps us understand the severity of class imbalance.<br>
•	Histograms: Plots of numerical features (e.g., LIMIT_BAL, AGE) give insight into their distribution (normal, skewed, etc.) and reveal outliers. <br>
•	Boxplots: Boxplots visualize the spread of bill and payment amounts, helping detect potential outliers.<br>
•	Correlation Heatmap: We generate a heatmap to show correlations between numeric features (e.g., BILL_AMT and PAY_AMT values over time). This helps identify multicollinearity—if two or more features are highly correlated, we might remove or combine them to avoid redundancy. 
<br>
<br>

a) **Distribution of Default Payment Next Month:** It generates a bar plot to show the count of clients who did and did not default in the default payment next month column of df, allowing visualization of class distribution in the target variable.<br>
<p align="center">
  <img src="https://github.com/user-attachments/assets/a5867cd0-c04f-40a9-9e2a-012695a16537"/></p>
  <p align="center">Distribution of Default Payment Next Month</p>
<p align="center">
  <img src="https://github.com/user-attachments/assets/18dc7475-8aca-4dad-ad53-1b5b55c27597"/></p>
<br>
<br>

**b) Distribution of Credit Limit (LIMIT_BAL)**: It creates a histogram with a density curve to show the distribution of credit limits (LIMIT_BAL) in df, helping visualize the spread and frequency of different credit limit values and the below figure is the output.
<p align="center">
  <img src="https://github.com/user-attachments/assets/b7c0fd9a-c99c-4805-a30e-0a6a0262638a"/></p>
  <p align="center"> Distribution of Credit Limit (LIMIT_BAL)</p>
<p align="center">
  <img src="https://github.com/user-attachments/assets/b7c0fd9a-c99c-4805-a30e-0a6a0262638a"/></p>
  <p align="center"> Output for Distribution of Credit Limit (LIMIT_BAL)</p>
  <br>
  <br>
  
**c) Age Distribution:** It creates a histogram with a density curve to show the distribution of AGE in df, highlighting the frequency and spread of ages in the dataset and below figure is the output. <br>
<p align="center">
  <img src="https://github.com/user-attachments/assets/caad23bc-07e6-4023-8b2c-f1f8104ac3b4"/></p>
  <p align="center">Age Distribution</p>
<p align="center">
  <img src="https://github.com/user-attachments/assets/88eb3c54-5697-4fbf-a12e-ff7748781b19"/></p>
  <p align="center">Output for Age Distribution</p>
<br>
<br>

**d) Correlation Heatmap of Features:** It generates a heatmap to display correlations between features in df, with annotations, colors indicating correlation strength, and a larger figure size for clarity.
<p align="center">
  <img src="https://github.com/user-attachments/assets/d15c7086-d345-4faf-8d3e-9e552e87adee"/></p>
  <p align="center">Correlation Heatmap of Features</p>
<p align="center">
  <img src="https://github.com/user-attachments/assets/3630769e-863c-4d76-bc77-137974f80740"/></p>
  <p align="center">Output for Correlation Heatmap of Features</p>
<br>
<br>

**4. Logistic Regression Tuning & Evaluation:** It scales features and trains a Logistic Regression model on the scaled training data, evaluates it with 5-fold cross-validation for accuracy, and outputs mean accuracy, standard deviation, and a classification report for predictions on the test set.
<p align="center">
  <img src="https://github.com/user-attachments/assets/b4222891-a8e5-4f8f-b9b6-6ce6c205494f"/></p>
  <p align="center">Logistic Regression classification report</p>
<p align="center">
  <img src="https://github.com/user-attachments/assets/0076d70b-4425-43f6-98b6-34ebc857e8b9"/></p>
  <p align="center">Output for Logistic Regression classification report</p>
<br>
<br>
<br> 

**5. Random Forest Tuning & Evaluation:** It trains a Random Forest model on the training data, evaluates it using 5-fold cross-validation, prints mean accuracy and standard deviation, generates a classification report for test predictions, and displays a confusion matrix heatmap.

<p align="center">
  <img src="https://github.com/user-attachments/assets/d224b45a-5434-4877-b95b-1f659d22ae0a"/></p>
  <p align="center">Random Forest Parameter Tuning
</p>
<p align="center">
  <img src="https://github.com/user-attachments/assets/96ff5b41-17e4-481b-87d9-84f5a4a2d2d2"/></p>
  <p align="center">Random Forest Parameter Tuning</p>
<p align="center">
  <img src="https://github.com/user-attachments/assets/a3b92462-c644-4a93-a389-b4621419aef2"/></p>
  <p align="center">Random Forest - Confusion Matrix</p>

**6. Gradio App Usage:** Gradio App Usage
We implemented a Gradio web interface to provide an interactive platform for credit card default predictions.<br>
Instructions:<br>
1.	Enter the Client Data: Fill in all the required fields with relevant client information, such as credit limit, bill amounts, repayment status, and payment amounts.<br>
2.	Submit the Data: Click the "Submit" button to generate the prediction. The app will indicate whether the client is likely to default or not default on their payment.<br>
3.	Error Handling: If any field is missing or the input data is invalid (e.g., non-numeric values), an error message will be shown, prompting the user to correct the input.<br>
This interface allows for easy testing of the prediction model, providing real-time results and enhancing usability for non-technical users.<br>
<p align="center">
  <img src="https://github.com/user-attachments/assets/3f86977f-b306-48b2-a9a4-606e6a674bf9"/></p>
  <p align="center">Code for Gradio app interface</p>
<p align="center">
  <img src="https://github.com/user-attachments/assets/7ec2ee51-2f7f-4bc7-8acd-9c1ab483b14d"/></p>
  <p align="center">Output for Gradio app interface</p>




