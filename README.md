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
a) **Distribution of Default Payment Next Month:**
<p align="center">
  <img src=""/></p>
  <p align="center">Checking for Missing Values in dataset</p>



  














