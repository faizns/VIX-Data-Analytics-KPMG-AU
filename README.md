# **Data Analytics Consulting Virtual Internship Experience - KPMG AU**

## 📂 **Overview**

KPMG is a global organization of independent professional firms that provides a range of services to organizations across various industries, government, and non-profit sectors. Its service areas include Audit, Assurance & Risk Consulting; Deals, Tax & Legal; Management Consulting; and Innovation & Digital Solutions.

Under the KPMG Digital Solutions service, as part of the Data, Analytics & Modeling team, we will effectively analyze data sets to help Sprocket Central Pty Ltd, a bike and bike accessories company, develop and optimize its marketing strategies.

The client provided KPMG with 3 datasets:
- Customer demographics
- Customer addresses
- Transactions
<br>

---

## 📂 **Task 1 - Data Quality Assessment**

### **Background Information**

Sprocket Central Pty Ltd needs help with its customer and transactions data. The organisation has a large dataset relating to its customers, but their team is unsure how to effectively analyse it to help optimise its marketing strategy. 

*"The importance of optimising the quality of customer datasets cannot be underestimated. The better the quality of the dataset, the better chance you will be able to use it drive company growth."*

The client provided KPMG with 3 datasets:
- Customer Demographic 
- Customer Addresses
- Transactions data in the past 3 months

### **Objectives**
- Review and evaluate the data based on Standard Data Quality Dimensions.
- Identify strategies to mitigate that issues.

### **Result**
[Check out the analysis in the notebook!](https://github.com/faizns/VIX-Data-Analytics-KPMG-AU/blob/main/Task%201%20-%20KPMG%20VIX.ipynb) <br>


| **Tabel Name**      | **No of Records** | **Distinct customer_id** | **Date Data Recieved** |
|---------------------|-------------------|--------------------------|------------------------|
| CustomerDemographic | 4000              | 4000                     | 2022-12-20             |
| CustomerAddres      | 3999              | 3999                     | 2022-12-20             |
| Transactions        | 20001             | 3494                     | 2022-12-20             |

<br>

#### 1. Accuracy : correct values
There are several columns with values that are inaccurate with the existing dataset.
- In **CustomerDemographic**, `DOB` is less able to provide insight into the dataset. From this, `DOB` has been converted to a new column **`Age`**.
- In **Transactions**, the values of `product_first_sold` date have Unix timestamp format. It has been converted to a **general timestamp**.<br>
    <br>

#### 2. Completeness : data field with values
Various columns have empty or missing values in certain records.
- In **CustomerDemographic**, the total percentage of **missing values reaches 30%** with the columns that have the highest percentage of `job_industry_category` and `job_title`. Based on the categorical data type and the distribution of values in each column, they have been **filled with the previous value**.
- In **Transactions**, the percentage of **missing values is only 2.78%**. These records are **still safe to remove** from the dataset, as they do not significantly affect the analysis or modeling results. <br>
<br> 

#### 3. Consistency : value free from contradiction
There are inconsistent datatypes and values for the same column.
- Datatype: **Remove unwanted characters and change the datatype** (e.g. object to numeric). Make sure that the same column in different tables has the same datatype.
    - `DOB`, `transaction_date` is recommended to be datetime.
    - `transaction_id`, `product_id`, `customer_id`, `product_first_sold_date `is recommended to be integer.
    - `standard_cost` is recommended to be float.
- Values: Replace the inconsistent value that has the least frequency of expression.
    - Column `gender` in the CustomerDemographics - "F", "Femel", to **"Female"**; "M" to **"Male"**.
    - Column `state` in the CustomerAddress - "New South Wales" to **"NSW"**, "Victoria" to **"VIC"**. <br>
    <br>

#### 4. Currency : value up to date
- In `deceased_indicator`, **CustomerDemographic** table, value **"Y" ware not current customers** and has been deleted because we want only live customers.<br>
<br>

#### 5. Relevancy : data items with value meta-data
- The `default` in the CustomerDemographic and `Unnamed: 13 to Unnamed: 23` in the **Transaction** table are columns that have no relevance to the dataset. They should be **deleted**.
- In **CustomerDemographic**, the **"U"** values in gender are not known what they represent. So they have been replaced based on the data distribution, **"Male"**.<br>
<br>

#### 6. Validity : data containing allowable values
- In the Transaction table, `standard_cost` has a **value that does not match** the format and **inconsistent** data entry. Remove unwanted characters and change the datatype accordingly.
- There are some records in `product_id = 0`, we can make sure and check the database if there is 0 is a number code of product.<br>
<br>

#### 7. Uniqueness : record that are duplicated
- No duplicate records<br>
<br>

---

## 📂 **Task 2 - Data Insights**

### **Background Information**
Sprocket Central Pty Ltd marketing team is looking to boost business by analysing their existing customer dataset to determine customer trends and behaviour. Using the existing 3 datasets (Customer demographic, customer address and transactions) as a labelled dataset, we will recommend which of these 1000 new customers should be targeted to drive the most value for the organisation. 


### **Objective**
- Built customer segmentation based on RFM model
- Analyzing customer trends, behaviour, and demographic

### **Result**
[Check out the analysis in the notebook!]() <br>
<br>

---

## 📂 **Task 3 - Data Insights and Presentation**

### **Background Information**
After building the model we need to present our results back to the client. A list of customers or algorithm won’t cut it with the client, we need to support our results with the use of visualisations.

### **Objective**
- Develop a dashboard

### **Result**
[Check out in the Tableau!]() <br>
<br>

<p align="center">
  <kbd> <img width="750" alt="msg" src="https://user-images.githubusercontent.com/115857221/217406894-3088170d-d115-42ba-94b5-1a72af175f9b.png"> </kbd> <br>
</p>
<br>
