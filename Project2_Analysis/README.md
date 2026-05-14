# 2️⃣nd Project - Analysis

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

![Power Query 1](images\01 Skills vs Salary - powerquery1.png)

- `data_jobs_skills`
