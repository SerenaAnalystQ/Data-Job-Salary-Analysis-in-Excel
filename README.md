# Data-Job-Salary-Analysis-in-Excel

This project extends the analysis conducted in the [Data Job Salary Dashboard](https://github.com/SerenaAnalystQ/Data-Job-Salary-Excel-Dashboard repository) and explores more analysis.

<img 
src="https://raw.githubusercontent.com/SerenaAnalystQ/Data-Job-Salary-Excel-Dashboard/main/images/Dashboard_Review.gif" 
width="850">

<p align="center">
Figure 1. Interactive Excel dashboard
</p>

## Introduction

This project explores salary patterns, regional compensation differences, and in-demand technical skills within the global data job market using Microsoft Excel.

The analysis was conducted using a real-world dataset containing job postings related to data and technology careers. The objective of the project was to transform raw job market data into structured analytical insights through data modeling, visualization, and business intelligence techniques within Excel.

The project emphasizes the practical application of:
- Power Query
- Power Pivot
- DAX
- Pivot Tables
- Pivot Charts
- Data Modeling
- Interactive Visualization

---

## Analytical Questions

The project was designed to address the following analytical questions:

1. Do jobs requiring more technical skills offer higher salaries?
2. How do salaries vary across different geographic regions?
3. What are the most in-demand technical skills within data-related careers?
4. Which technical skills are associated with the highest salaries?

---
## Dataset Overview

The dataset contains real-world job posting information from 2023 related to data and technology careers.

### Dataset Information

- Total Records: 32,673 job postings
- Multiple structured attributes including:
  - Job Title
  - Salary
  - Country
  - Job Location
  - Technical Skills
  - Job Platform
  - Employment Type

### Covered Roles

The dataset includes positions such as:
- Data Analyst
- Data Scientist
- Data Engineer
- Machine Learning Engineer
- Software Engineer
- Business Analyst

The dataset served as the foundation for all analytical modeling and visual reporting within the project.

---

# 1️⃣ Do more skills get you better pay?

### 🔍 Skill: Power Query (ETL)

#### 📥 Extract

- I first used Power Query to extract the original data (`data_salary_all.xlsx`) and create two queries:
    - 🗃️ First one with all the data jobs information.
    - 🔧 The second listing the skills for each job ID.

#### 🔄 Transform

- Then, I transformed each query by changing column types, removing unnecessary columns, cleaning text to eliminate specific words, and trimming excess whitespace.
    - 📊 data_jobs_all

        <img src="Image/QueryStep1.png" width="300">

    - 🛠️ data_job_skills

        <img src="Image/QueryStep2.png" width="300">

#### 🔗 Load

- Finally, I loaded both transformed queries into the workbook, setting the foundation for my subsequent analysis.
    - 📊 data_jobs_all

        <img src="Image/QueryReview1.png" width="700">

    - 🛠️ data_job_skills

        <img src="Image/QueryReview2.png" width="700">

### 📊 Analysis

#### 💡 Insights

- 📈 There is a positive correlation between the number of skills requested in job postings and the median salary, particularly in roles like Senior Data Engineer and Data Scientist.
- 💼 Roles that require fewer skills, like Business Analyst, tend to offer lower salaries, suggesting that more specialized skill sets command higher market value.

<img src="Image/Chart1.png" width="700">

## 2️⃣ What’s the salary for data jobs in different regions?

### 🧮 Skills: PivotTables & DAX

#### 📈Pivot Table

- 🔢 I created a PivotTable using the Data Model I created with Power Pivot.
- 📊 I moved the `job_title_short` to the rows area and `salary_year_avg` into the values area.
- 🧮 Then I added new measure to calculate the median salary for United States jobs.
    ```
    =CALCULATE(
        MEDIAN(data_jobs_all[salary_year_avg]),
        data_jobs_all[job_country] = "United States")
    ```

#### 🧮 DAX

- To calculate the median year salary I used DAX.

    ```
    Median Salary := MEDIAN(data_jobs_all[salary_year_avg])
    ```

### 📊 Analysis

#### 💡 Insights

- 💼 Job roles like Senior Data Engineer and Data Scientist command higher median salaries both in the US and internationally, showcasing the global demand for high-level data expertise.
- 💰 The salary disparity between US and Non-US roles is particularly notable in high-tech jobs, which might be influenced by the concentration of tech industries in the US.

    <img src="Image/Chart2.png" width="700">

#### **🤔 So What**

- These salary insights are important for planning and salary negotiations, helping professionals and companies align their offers with market standards while considering geographical variations.

## 3️⃣ What are the top skills of data professionals?

### 🔧 Skill: Power Pivot

#### 💪 Power Pivot

- 🔗 I created a data model by integrating the `data_jobs_all` and `data_jobs_skills` tables into one model.
- 🧹 Since I had already cleaned the data using Power Query; Power Pivot created a relationship between these two tables.

#### 🔗 Data Model

- I created a relationship between my two tables using the `job_id` column.

    <img src="Image/Chart2.png" width="700">

#### 📃 Power Pivot Menu

- The Power Pivot menu was used to refine my data model and makes it easy to create measures.
<img src="Image/2_Project_Analysis_Screenshot6.png" width="700">


### 📊Analysis

#### 💡Insights

- 💻 SQL and Python dominate as top skills in data-related jobs, reflecting their foundational role in data processing and analysis.
- ☁️ Emerging technologies like AWS and Azure also show significant presence, underlining the industry's shift towards cloud services and big data technologies.

    <img src="Image/Chart3.png" width="700">

#### 🤔So What

- Understanding prevalent skills in the industry not only helps professionals stay competitive but also guides training and educational programs to focus on the most impactful technologies.

## 4️⃣ What’s the pay of the top 10 skills?

### 📊 Skill: Advanced Charts (Pivot Chart)

#### 📈 PivotChart

- I created a combo PivotChart to plot median salary and skill likelihood (%) from my PivotTable.
    - 🪙 **Primary Axis:** Median Salary (as a Clustered Column)
    - 👍 **Secondary Axis:** Skill Likelihood (as a Line with Markers)
- To customize the chart, I added a title axis title, removed the lines (skill likelihood), and changed the markers to diamonds.

### 📊 Analysis

#### 💡Insights

- 💰 Higher median salaries are associated with skills like Python, Oracle, and SQL, suggesting their critical role in high-paying tech jobs.
- 📉 Skills like PowerPoint and Word have the lowest median salaries and likelihood, indicating less specialization and demand in high-salary sectors.

    <img src="Image/Chart4.png" width="700">

### 🤔So What

- This chart highlights the importance of investing time in learning high-value skills like Python and SQL, which are evidently tied to higher paying roles, especially for those looking to maximize their salary in the tech industry.
