# 2️⃣nd Project - Analysis

_This project is the sample of my learned skills in Excel course and show off my progress and positive to-do attitude. Also learned SQL and now working on PowerBI._

---

In Excel, I've done a few questions below with following Excel skills:

- 📊 Pivot Tables
- 📈 Pivot Charts
- 🧮 DAX (Data Analysis Expressions)
- 🔍 Power Query
- 💪 Power Pivot

## Questions

1. **Do more skills get you better pay?**
2. **What’s the salary for data jobs in different regions?**
3. **What are the top skills of data professionals?**
4. **What’s the pay for the top 10 skills?**

### Data jobs dataset

- include real-world data science job information from 2023
- Information of: 👨‍💼 Job titles, 💰 Salaries, 📍 Locations, 🛠️ Skills

## 1️⃣ Do more skills get you better pay?

### 🔍 Skill: Power Query (ETL)

**📥 Extract**

First, I used Power Query to extract the original data (`data_salary_all.xlsx`) and create two queries:

- 🗃️ First one with all information of data jobs
- 🔧 The second listing the skills for each job ID.

**🔄 Transform & Load**

Then, I transformed each query by changing column types, removing unnecessary columns, cleaning text to eliminate specific words, and trimming excess whitespace.

- `data_jobs_salary`
  ![Power Query 1](/images/01_Skills_vs_Salary_powerquery1.png)

- `data_jobs_skills`
  ![Power Query 2](/images/01_Skills_vs_Salary_powerquery2.png)

**📊 Analysis**

- In the picture below there is clearly see that more skills = higher (median) salary
- Roles like Business Analyst and Data Analysit required less skill but also lower median salary
  ![1Chart1](/images/01_Skills_vs_Salary_chart.png)

## 2️⃣ What’s the salary for data jobs in different regions?

### 🧮 Skills: PivotTables & DAX

**📈Pivot Table & DAX**

- Firstly, I created a PivotTable using the Data Model I created with Power Pivot
- Then, moved the job_title_short to the rows area and calculated median of `salary_year_avg` with DAX and moved it into the values area.

```
Median Salary:=MEDIAN(data_jobs_salary[salary_year_avg])
```

- Finally, I added new measure to calculate the median salary for United States(US) and non-US jobs

```
=CALCULATE([Median Salary];data_jobs_salary[job_country]="United States")

--

=CALCULATE([Median Salary];data_jobs_salary[job_country]<>"United States")
```

**📊 Analysis**

- You can try and find what job role and median is the best depending on the country and compare it with US or non-US median salary
  ![2PivotTable1](/images/02_Salary_Analysis_pivottable1.png)

## 3️⃣ What are the top skills of data professionals?

### 🔧 Skill: Power Pivot

- I created a data model by integrating the data_jobs_all and data_jobs_skills tables into one model created a relationship between these two tables
  ![3PowerPivot1](/images/03_Skill_Job_Analysis_powerpivot1.png)

**📊Analysis**

- I used jobs like Data & Business Analysts in this chart, to see more closely to this _"entry"_ jobs to Data field
- SQL, Excel and some Visualization tool (Tableau & PowerBI gives in sum 4800 jobs!) are the most required. Right after that is Python.
  ![3Chart1](/images/03_Skill_Job_Analysis_chart1.png)

## 4️⃣ What's the pay of the top 10 skills for Data & Business Analysts?

### 📊 Skill: Advanced Charts (Pivot Chart)

- I created a combo PivotChart to plot median salary and skill likelihood (%) from my PivotTable.
  - **Primary Axis:** Median Salary (as a Clustered Column)
  - **Secondary Axis:** Skill Likelihood (as a Line with Markers)

**📊 Analysis**

- The most requested skill SQL is't the best paid skill
- On the other hand, visualization tool Tableau has the best pay from the four most required skills (SQL, Excel, Tableau and PowerBI)
  ![4Chart1](/images/04_Skill_Salary_Analysis_chart.png)
