 
# Health Care Data Analysis Using SQL

## Project Overview

This project involves analyzing a healthcare dataset obtained from **Kaggle** using SQL. The goal is to explore patient-related information and derive insights into patient demographics, hospitalizations, and age distributions. Through a series of SQL queries, the project demonstrates how healthcare data can be used to uncover patterns and trends within a hospital environment.

The dataset contains various patient attributes like age, admission details, and other critical data points that are used to perform detailed analysis and generate meaningful insights.

---

## Dataset Information

The dataset used in this project is sourced from Kaggle, a well-known platform for datasets and data science competitions. It contains patient records, which include the following key columns:
- **PatientID:** Unique identifier for each patient.
- **Age:** The age of the patient.
- **Gender:** The patient's gender.
- **Admission_Date:** The date when the patient was admitted.
- **Health_Condition:** A brief description of the patient's health status.


## Project Structure

This project is divided into several sections, starting with the creation of the healthcare database and moving on to various SQL queries that provide insights from the dataset.

### 1. **Database Creation**
   - **Creating the Healthcare Database:**  
     The database `Healthcare` is created to store the patient data and perform analysis. It contains a single table also named `Healthcare`.
     
   - **Selecting the Database:**  
     The `USE Healthcare;` command ensures that all subsequent SQL queries are executed within the correct database.

### 2. **Viewing Data and Table Structure**
   - **View the Data:**  
     The `SELECT * FROM healthcare;` query retrieves all records in the dataset, allowing us to view the patient data.
     
   - **Table Description:**  
     The `DESC Healthcare;` command provides a detailed structure of the table, displaying the column names, data types, and other metadata.

---

## SQL Queries and Insights

The project includes several SQL queries designed to extract meaningful insights from the dataset. Below are some key queries and their purposes:

### 1. **Total Record Count**
   - **Query:**
     ```sql
     SELECT COUNT(*) FROM Healthcare;
     ```
   - **Description:**  
     This query counts the total number of records in the `Healthcare` table, providing an overview of the dataset size.

   - **Sample Output:**  
     | Total Records |
     |---------------|
     | 1000          |

### 2. **Maximum Age of Admitted Patients**
   - **Query:**
     ```sql
     SELECT MAX(age) AS Maximum_Age FROM Healthcare;
     ```
   - **Description:**  
     This query retrieves the maximum age of patients admitted to the healthcare facility. It helps in identifying the oldest patient in the dataset.

   - **Sample Output:**  
     | Maximum Age |
     |-------------|
     | 85 years    |

### 3. **Average Age of Hospitalized Patients**
   - **Query:**
     ```sql
     SELECT ROUND(AVG(age), 0) AS Average_Age FROM Healthcare;
     ```
   - **Description:**  
     This query calculates the average age of patients admitted to the hospital. It helps identify the general age distribution of patients.

   - **Sample Output:**  
     | Average Age |
     |-------------|
     | 45 years    |

### 4. **Age-Wise Distribution of Patients**
   - **Query:**
     ```sql
     SELECT AGE, COUNT(AGE) AS Total
     FROM Healthcare
     GROUP BY age
     ORDER BY AGE DESC;
     ```
   - **Description:**  
     This query groups patients by age and counts the number of patients for each unique age. The results are sorted in descending order by age, showing which age groups have the highest number of hospitalizations.

   - **Sample Output:**
     | Age  | Number of Patients |
     |------|--------------------|
     | 85   | 5                  |
     | 75   | 8                  |
     | 70   | 20                 |
     | 65   | 18                 |
     | ...  | ...                |

### 5. **Minimum Age of Patients**
   - **Query:**
     ```sql
     SELECT MIN(age) AS Minimum_Age FROM Healthcare;
     ```
   - **Description:**  
     This query identifies the youngest patient in the dataset.

   - **Sample Output:**
     | Minimum Age |
     |-------------|
     | 18 years    |

---

## Insights from the Analysis

This project provides several insights into the patient data, including:
- The **maximum age** of patients admitted is 85 years.
- The **average age** of patients is 45 years.
- An **age-wise breakdown** shows that most patients fall between 30 and 50 years of age, indicating a concentration of middle-aged individuals being admitted.

