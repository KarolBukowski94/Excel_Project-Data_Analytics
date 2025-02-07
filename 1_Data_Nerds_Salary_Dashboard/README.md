# Data Nerds Salary Dashboard

🎯 The [dashboard](1_Data_Nerds_Salary_Dashboard.xlsx) helps job seekers explore salary trends across various data-related job titles, providing essential insights into expected salaries for their desired roles. The tool highlights salary differences based on position, country, and job schedule type, enabling users to make well-informed career decisions.

![Data Nerds Salary Dashboard](/0_Resources/Images/1_Data_Nerds_Salary_Dashboard/1_Data_Nerds_Salary_Dashboard.gif)

## Excel Skills Used

- **📉 Charts**
- **🧮 Formulas and Functions**
- **❎ Data Validation**

## Dashboard Build

### 📉 Charts

#### 📊 Data Science Job Salaries - Bar Chart

![Job Salaries Bar Chart](/0_Resources/Images/1_Data_Nerds_Salary_Dashboard/2_Job_Salaries_Bar_Chart.PNG)

- 🛠️ **Excel Features:** Utilized bar chart feature (with formatted salary values) and optimized layout for clarity.
- 🎨 **Design Choice:** Horizontal bar chart for visually comparing median salaries.
- 📉 **Data Organization:** Sorted job titles by descending salary for improved readability.
- 💡 **Insights Gained:** This enables quick identification of salary trends, noting that Senior roles and Engineers are higher-paying than Analyst roles.

#### 🗺️ Country Median Salaries - Map Chart

![Country Salary Map Chart](/0_Resources/Images/1_Data_Nerds_Salary_Dashboard/3_Country_Salary_Map_Chart.gif)

- 🛠️ **Excel Features:** Utilized Excel's map chart feature to plot median salaries globally.
- 🎨 **Design Choice:** Color-coded map to visually differentiate salary levels across regions.
- 📊 **Data Representation:** Plotted median salary for each country with available data.
- 👁️ **Visual Enhancement:** Improved readability and immediate understanding of geographic salary trends.
- 💡 **Insights Gained:** Enables quick grasp of global salary disparities and highlights high/low salary regions.

### 🧮 Formulas and Functions

#### 💰 Median Salary by Job Titles

```
=MEDIAN(
IF(
    (jobs[job_title_short]=A2)*
    (jobs[job_country]=country)*
    (ISNUMBER(SEARCH(type,jobs[job_schedule_type])))*
    (jobs[salary_year_avg]<>0),
    jobs[salary_year_avg]
)
)
```

- 🔍 **Multi-Criteria Filtering:** Checks job title, country, schedule type, and excludes blank salaries.
- 📊 **Array Formula:** Utilizes `MEDIAN()` function with nested `IF()` statement to analyze an array.
- 🎯 **Tailored Insights:** Provides specific salary information for job titles, regions, and schedule types.
- **🔢 Formula Purpose:** This formula populates the table below, returning the median salary based on job title, country, and type specified.

🍽️ Background Table

![Background Table Salary](/0_Resources/Images/1_Data_Nerds_Salary_Dashboard/4_Background_Table_Salary.PNG)

📉 Dashboard Implementation

![Dashboard Implementation Salary](/0_Resources/Images/1_Data_Nerds_Salary_Dashboard/5_Dashboard_Implementation_Salary.PNG)

#### ⏰ Count of Job Schedule Type

```
=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))
```

- 🔍 **Unique List Generation:** This Excel formula below employs the `FILTER()` function to exclude entries containing "and" or commas, and omit zero values.
- **🔢 Formula Purpose:** This formula populates the table below, which gives us a list of unique job schedule types.

🍽️ Background Table

![Background Table Type](/0_Resources/Images/1_Data_Nerds_Salary_Dashboard/6_Background_Table_Type.PNG)

📉 Dashboard Implementation:

![Dashboard Implementation Type](/0_Resources/Images/1_Data_Nerds_Salary_Dashboard/7_Dashboard_Implementation_Type.PNG)

### ❎ Data Validation

#### 🔍 Filtered List

- 🔒 **Enhanced Data Validation:** Implementing the filtered list as a data validation rule under the `Job Title`, `Country`, and `Type` option in the Data tab ensures:
    - 🎯 User input is restricted to predefined, validated schedule types
    - 🚫 Incorrect or inconsistent entries are prevented
    - 👥 Overall usability of the dashboard is enhanced

![Data Validation](/0_Resources/Images/1_Data_Nerds_Salary_Dashboard/8_Data_Validation.gif)

## Conclusion

This interactive tool provides insights into how job title, location, and job type influence final salary, helping users make informed career decisions. The dashboard supports job seekers in negotiating fair compensation and is a valuable resource for professionals transitioning into higher-paying roles in the data science industry.
