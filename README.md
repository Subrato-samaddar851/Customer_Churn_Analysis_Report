# Customer_Churn_Analysis_Report
# Internet Service Customer Churn Analysis (Excel)

<p>In this analysis, we will explore the Customer Churn dataset to understand the factors that lead to customers discontinuing their internet service. We will also offer recommendations on how to reduce churn and retain customers.</p>

<ol>
  <li>
      <b>Is the difference in LTV between churned and non-churned customers statistically significant?</b>
      <p>Determine how much impact the company can have due to churned customers.</p>
  </li>
  <li><b>Is Subscription Type correlated with customer churn?</b>
      <p>Determining which subscription type is more likely to result in customer churn.</p>
  </li>
  <li><b>Which Contract Length leads to higher customer churn?</b>
    <p>Identifying the contract length that has the highest rate of customer churn.</p>
  </li>
  <li><b>Is payment delay related to customer churn?</b>
    <p>Analyzing the relationship between payment delays and customer churn.</p>
  </li>
  <li><b>Is there any correlation between Gender, Age, and Customer Churn?</b>
    <p>Identifying the correlation between gender, age, and customer churn.</p>
  </li>
  <li><b>Which Tenure category is more likely to result in customer churn?</b>
    <p>Identifying the tenure category that is most likely to experience customer churn.</p>
  </li>
</ol>

<p><b>Dataset Source: </b>https://www.kaggle.com/datasets/muhammadshahidazeem/customer-churn-dataset/data</p>
 
## Cleaning the dataset
### Step 1: Understand the dataset

<p>The dataset contains 64374 records of customer realated data. <br>There are 11 columns of data as below: </p>

<ol>
  <li><b>CustomerID</b>: A unique identifier for each customer. This helps to distinguish each customer individually.</li>
  <li><b>Age</b>: The age of the customer.</li>
  <li><b>Gender</b>: The gender of the customer (e.g., Male, Female).</li>
  <li><b>Tenure</b>: The length of time (in months) that the customer has been using the service.</li>
  <li><b>Support Calls</b>: The number of times the customer has contacted customer support. This might indicate how much assistance the customer needs or how many issues they have encountered.</li>
  <li><b>Payment Delay</b>: Indicates how frequently the customer has delayed payments.</li>
  <li><b>Subscription Type</b>: The type of subscription the customer has chosen. This could include different service plans or levels (e.g., Basic, Standard, Premium).</li>
  <li><b>Contract Length</b>: The duration of the contract the customer has agreed to (e.g., 1 year, 2 years).</li>
  <li><b>Total Spend</b>: The total amount of money the customer has spent on the service over their tenure.</li>
  <li><b>Last Interaction</b>: The last time the customer interacted with the service or company. This could be the last purchase, login, or contact with customer support.</li>
  <li><b>Churn</b>: This is the key column indicating whether the customer has stopped using the service or product. In which, "1" indicates that the customer has churned (left the service), and "0" indicates that the customer is still active.</li>
</ol>

<p>Firstly, I converted the cells into a table by using <kbd>Cmd</kbd> + <kbd>T</kbd> in Excel.</p>

### Step 2: Check for Duplicates Records

<p>After understanding the dataset, I check for any duplicates first by Excel built-in functionality, "Remove Duplicates".</p>

### Step 3: Check for Any Blanks or Irregular Values in Records

<p>By using conditional formatting, I highlighted the blank cells. Since the highlighted rows were all empty, I deleted them. I didn't find any blank cells or irregular values.</p>

## Preparing the dataset
### Creating new columns

<p>I added a new column called "Total Count" and filled it with the value 1. This column will help in calculating the churn rate when creating a pivot table.</p>
<p>Next, I categorized the "Age" column into three groups and created a new column called "Age Categories" using the IF formula. The three age categories are "Adolescents" which is between 18 and 34, "Middle-aged" which is between 35 and 49 and "Seniors" which are more than 49.</p>
<p>After that, I converted the "Tenure" in months to "Tenure in Years" by dividing by 12 and filled the values in a new column called "Tenure (Year)."</p>
<p>Finally, I categoriezed "Payment Dealy" column to Long Delay and Short Delay in filled the values in a new column called "Payment Delay Categories".</p>

### Changing the Data Type
<p>I changed the data type of the "Total Spend" column from General to Dollar Currency.</p>

## Define Metrics for Dashboard
<p>We create the following pivot tables to answer our business questions.</p>

### Metric 1: Lifetime Value of Churned and Non-Churned Customers
<b>Values:</b> CustomerID (By Count), Total Spend (By Sum), Tenure_Year (Average) <br>
<b>Rows:</b> Churn<br>
<b>Columns:</b> Values<br>

#### Calculating LTV for Churned Customer
<p>First, we need to calculate the "Average Revenue per Churned Customer." To do this, we divide the total spend by the number of churned customers from the pivot table above. Next, we multiply this result by the average tenure of churned customers from the same table. This will give us the LTV for churned customers.</p>

#### Calculating LTV for Non-Churned Customer
<p>First, we need to calculate the "Average Revenue per Non-Churned Customer." To do this, we divide the total spend by the number of non-churned customers from the pivot table above. Next, we multiply this result by the average tenure of non-churned customers from the same table. This will give us the LTV for non-churned customers.</p>

### Metric 2: Churn Rate by Subscription Type
<b>Values:</b> Churn Rate (By Sum) <br>
<b>Rows:</b> Subscription Type<br>

### Metric 3: Number of Churns by Contract Length
<b>Values:</b> Churn (By Sum)<br>
<b>Rows:</b> Contract Length

### Metric 4: Churn Rate by Payment Delay
<b>Values:</b> Churn Rate (By Sum)<br>
<b>Rows:</b> Payment Delay Category<br>

### Metric 5: Number of Churns by Age Group and Gender
<b>Values:</b> Churn (By Sum)<br>
<b>Rows:</b> Age Category<br>
<b>Columns:</b> Gender<br>

### Metric 6: Number of Churns by Tenure (Year)
<b>Values:</b> Churn (By Sum)<br>
<b>Rows:</b> Tenure<br>

## Creating Charts for Certain Metrics

### For Metric 2, Churn Rate by Subscription Type
<p>I created <b>Doughnut Chart</b>, for three Subscription Type.</p>
<img width="417" alt="Screenshot 2024-08-01 at 8 21 46 PM" src="https://github.com/user-attachments/assets/4f2867d7-24f9-4bb0-9bd6-ae15dbb3d3c7">

### For Metric 3, Number of Churns by Contract Length
<p>I created <b>Bar Chart</b>, as Contract Length in x-axis and Number of Churns in y-axis.</p>
<img width="480" alt="Screenshot 2024-08-01 at 8 28 23 PM" src="https://github.com/user-attachments/assets/bc5174b5-ef8f-48c2-bf98-02878e7737c6">

### For Metric 4: Churn Rate by Payment Delay
<p>I created <b>Pie Chart</b>, for two types of Payment Delay. </p>
<img width="417" alt="Screenshot 2024-08-01 at 8 22 02 PM" src="https://github.com/user-attachments/assets/642e2c6a-ea44-4233-8d60-428677aa4c82">

### For Metric 5, Number of Churns by Age Group and Gender
<p>I again created <b>Line Chart</b>, as Age Group in x-axis and Number of Churns in y-axis.</p>
<img width="480" alt="Screenshot 2024-08-01 at 8 29 34 PM" src="https://github.com/user-attachments/assets/db6c1033-871c-4311-a59e-0200f08ae102">

### For Metric 6, Number of Churns by Tenure (Year)
<p>I created <b>Line Chart</b>, as Tenure (Year) in x-axis and Number of Churns in y-axis.</p>
<img width="480" alt="Screenshot 2024-08-01 at 8 30 39 PM" src="https://github.com/user-attachments/assets/ac97246e-dcef-4a2b-8424-9bad39c500f3">


### Creating Slicer
<p>I created a slicer to manipulate the data shown in charts. By using these tools, we can gain different insights through filtering.</p>

## Dashboard
![Screenshot 2025-04-14 at 6 24 17 PM](https://github.com/user-attachments/assets/26b47359-e16d-470e-bd03-212cfc133a52)

## Analysis From Dashboard

<p>Analyzing the dashboard provides an overview of the factors contributing to customer churn, which can affect the company's performance. By observing these factors, we can make recommendations to help retain our existing customers and prevent churn.</p>

### Analysis 1: Lifetime value of Churned and Non-Churned Customer
<p>The data clearly indicates that churned customers have a significantly higher LTV than non-churned customers. Therefore, it is crucial to focus on retaining existing customers rather than solely aiming to acquire new ones. We need to survey and understand why these high-value customers are leaving.</p>

### Analysis 2: Churn Rate by Subscription Type
<p>The chart indicates that there is no significant relationship between subscription type and customer churn.</p>

### Analysis 3: Number of Churns by Contract Length
<p>Monthly contracts have the highest customer churn, quarterly contracts have the lowest, and annual contracts fall in between. We should focus our marketing efforts on converting monthly contracts to quarterly or annual contracts.</p>

### Analysis 4: Churn Rate by Payment Delay
<p>88% of customers with longer payment delays are likely to churn. This indicates that payment delays have a direct impact on customer churn.</p>

### Analysis 5, Number of Churns by Age Group and Gender
<p>Male customers tend to be more loyal than female customers. However, Senior(older age) groups are more likely to churn for both genders. We should implement more female-centric marketing strategies to reduce churn among female customers.</p>

### Analysis 6, Number of Churns by Tenure (Year)
<p>The highest number of churns occurs at 3 to 4 years of tenure. We need to investigate why these customers are leaving, as it significantly impacts company revenue.</p>
