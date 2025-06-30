# Credit_Card_Financial_Dashboard
Power BI Dashboad
# Project Objective: 
To develop a comprehensive credit card weekly dashboard that provides real-time insights into key performance metrics and trends, enabling stakeholders to monitor and analyze credit card operations effectively.
# Steps:
1. I have created a database in PostgreSQL.
   CREATE DATABASE ccdb;
2. I have created a two separate tables: cc_detail, cust_detail inside ccdb database.
   CREATE TABLE cc_detail;
   CREATE TABLE cust_detail;
3. For importing data from .CSV files, I have created columns inside these two tables and column names are same as given in the .csv files.

   --For cc_detail
   CREATE TABLE cc_detail (
    Client_Num INT,
    Card_Category VARCHAR(20),
    Annual_Fees INT,
    Activation_30_Days INT,
    Customer_Acq_Cost INT,
    Week_Start_Date DATE,
    Week_Num VARCHAR(20),
    Qtr VARCHAR(10),
    current_year INT,
    Credit_Limit DECIMAL(10,2),
    Total_Revolving_Bal INT,
    Total_Trans_Amt INT,
    Total_Trans_Ct INT,
    Avg_Utilization_Ratio DECIMAL(10,3),
    Use_Chip VARCHAR(10),
    Exp_Type VARCHAR(50),
    Interest_Earned DECIMAL(10,3),
    Delinquent_Acc VARCHAR(5)
    );
   
   --For cust_detail
   CREATE TABLE cust_detail (
    Client_Num INT,
    Customer_Age INT,
    Gender VARCHAR(5),
    Dependent_Count INT,
    Education_Level VARCHAR(50),
    Marital_Status VARCHAR(20),
    State_cd VARCHAR(50),
    Zipcode VARCHAR(20),
    Car_Owner VARCHAR(5),
    House_Owner VARCHAR(5),
    Personal_Loan VARCHAR(5),
    Contact VARCHAR(50),
    Customer_Job VARCHAR(50),
    Income INT,
    Cust_Satisfaction_Score INT
    );
5. Copy csv data into SQL
   -- copy cc_detail table

   COPY cc_detail
   FROM 'D:\credit_card.csv' 
   DELIMITER ',' 
   CSV HEADER;


   -- copy cust_detail table

   COPY cust_detail
   FROM 'D:\customer.csv' 
   DELIMITER ',' 
   CSV HEADER;
   # Note:
   # Error: When I am copying data it is showing an error that datestyle format is not not valid for PostgreSQL.
   # Solution: Update the Datestyle Setting: Set the datestyle explicitly for your session using the following command:
               SET datestyle TO 'ISO, DMY';

           
6. As database is ready. Now open Power BI to import data from SQL database.
   * In home tab click on get data
   * Click on PostgreSQL database choose 'ccdb' database
   * now choose tables 'cc_detail', 'cust_detail'
   * Load Data
   * Now Data Procesing
   * DAX query for new measures and new columns
   * Designed KPI's focused dashboard
   * Prepared data-driven insights
   * Exported dashboard into pdf format
   * Shared with the stakeholders.
     
# Insights:
   --Project Insights- Week 53 (31st	Dec)
 
   --WoW change:
    Revenue increased by 28.8%,
    Total Transaction Amt & Count increased by 33.56% & 3.57%
    Customer count increased by 28.3%
   
   --Overview YTD:
    Overall revenue is 57M
    Total interest is 8M
    Total transaction amount is 46M
    Male customers are contributing more in revenue 31M, female 26M
    Blue & Silver credit card are contributing to 93% of overall transactions
    TX, NY & CA is contributing to 68%
    Overall Activation rate is 57.5%
    Overall Delinquent rate is 6.06%
    Bills expenses are contributing more in revenue 14M 

# Action items:
  As per insights company should plan some monetary benefits like cashbacks, discounts etc. 
  For the customers having Blue or Silver credit card from TX, NY or CA to boost their revenue.

    




