## 1️⃣ Dashboard: Country-Based Salary Analysis

<img width="600" height="308" alt="Country-Based Dashboard Demo" src="../screenshots/dashboard_demo.gif" />

This dashboard provides a comprehensive analysis of 2023 data science job salaries across countries, job titles, and employment types. It helps visualize salary trends, compare job types, and identify geographic salary disparities using interactive Excel charts and formulas.

## Excel Skills Used

- **📉 Charts**
- **🧮 Formulas and Functions**
- **🔒 Data Validation**

## Dashboard Build

### 📉 Charts

#### 📊 Data Science Job Salaries - Bar Chart
<img width="408" height="353" alt="title" src="https://github.com/user-attachments/assets/ed74e007-8334-40ea-b967-b3fdf274ecb2" />  

- **Excel Features:** Utilized bar chart feature (with formatted salary values) and optimized layout for clarity.
- **Data Organization:** Sorted job titles by descending salary for improved readability.
- **Insights Gained:** This enables quick identification of salary trends, noting that Senior roles and Engineers are higher-paying than Analyst roles.

#### 🗺️ Country Median Salaries - Map Chart
<img width="371" height="271" alt="image" src="https://github.com/user-attachments/assets/7a768ece-fedc-43a6-854a-48103479d133" />  

- **Excel Features:** Utilized Excel's map chart feature to plot median salaries globally.
- **Data Representation:** Plotted median salary for each country with available data.
- **Visual Enhancement:** Improved readability and immediate understanding of geographic salary trends.
- **Insights Gained:** Enables quick grasp of global salary disparities and highlights high/low salary regions.

#### 💼 Job Type - Bar Chart
<img width="327" height="357" alt="type" src="https://github.com/user-attachments/assets/0d533106-f3ca-46d8-9581-4034db268e53" />  

- **Excel:** Bar chart showing salary by job type (Full-time, Part-time, Internship, etc.).  
- **Data:** Job types sorted by descending salary for clarity.  
- **Insight:** Highlights which job types offer higher pay, enabling quick salary comparison across employment types.

### 🧮 Formulas and Functions

#### 💰 Median Salary by Job Titles

```
=MEDIAN(
    IF(
        (jobs[job_title_short]=A3)*
        (jobs[salary_year_avg]<>0)*
        (jobs[job_country]=country)*
        (ISNUMBER(SEARCH(type,jobs[job_schedule_type]))),
        jobs[salary_year_avg]
    )
)

```

- **🔢 Formula Purpose:** This formula populates the table, returning the median salary based on job title, country, and type specified.
- **Multi-Criteria Filtering:** Checks job title, country, schedule type, and excludes blank salaries.
- **Array Formula:** Utilizes `MEDIAN()` function with nested `IF()` statement to analyze an array.
  

#### ⏰ Count of Job Schedule Type

```
=FILTER(M2#,NOT(ISNUMBER(SEARCH("and",M2#)))*(M2#<>0))
```
- **🔢 Formula Purpose:** This formula populates the table, which gives a list of unique job schedule types.
- **Unique List Generation:** This Excel formula employs the `FILTER()` function to exclude entries containing "and" or commas, and omit zero values.
  

### 🔒 Data Validation

#### 🔍 Filtered List

- Implementing the filtered list as a data validation rule under the `Job Title`, `Country`, and `Type` options ensures:
    - User input is restricted to predefined, validated schedule types
    - Incorrect or inconsistent entries are prevented
    - Overall usability of the dashboard is improved

---

## 2️⃣ Dashboard: Data Science Jobs Overview

<img width="600" height="308" alt="Jobs Overview Dashboard Demo" src="../screenshots/dashboard_demo_2.gif" />

This project is an **interactive Excel dashboard** providing a comprehensive overview of the data science job market in 2023. It leverages pivot tables, advanced Excel calculations, and dynamic slicers to analyze job distribution, salary trends, and monthly hiring patterns.

The dashboard was designed to:
- Provide a **clear overview** of the data science job market.  
- Highlight **high-demand roles** and **salary benchmarks**.  
- Analyze **temporal trends** in job openings for informed decision-making.

## Excel Skills Used

- **📊 Pivot Tables**
- **📈 Pivot Charts**
- **🔘 Slicers & Trendlines**

## Dashboard Build

### 📉 Charts

1. **Which Data Role Is Most Common?**  
   - Column chart showing distribution of job roles, grouped into primary, senior, and other data jobs.

2. **What is the Top Paying Job in Data Science?**  
   - Column chart ranking job roles by average yearly salary.

3. **How Are Jobs Trending Over Time?**  
   - Line chart showing job postings by month, including a trendline for visualizing overall growth.

### 🔄 Interactive Slicers

The dashboard includes slicers to filter data by:
- **Country**  
- **Job Group** (Primary, Senior, Other)  
- **Quarter** (for date-based trends)  

This allows users to dynamically analyze job count, salary, and trends across different dimensions.
