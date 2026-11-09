<div align="center">

# 📊 HR Analytics Dashboard

### Who is leaving, why, and what can HR do about it?

An interactive **Power BI** dashboard that turns 1,417 employee records into a clear picture of workforce attrition.

![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Dataset](https://img.shields.io/badge/Records-1%2C417-0A66C2?style=for-the-badge)
![Columns](https://img.shields.io/badge/Features-38-2E8B57?style=for-the-badge)
![Focus](https://img.shields.io/badge/Focus-Employee%20Attrition-D9534F?style=for-the-badge)

</div>

---

## 🎯 Project Overview

Employee turnover is expensive: it means lost knowledge, recruitment costs, and lower team morale. This project analyses an HR dataset of **1,417 employees across 7 departments** to answer three practical questions:

1. **How big is the attrition problem?** (overall rate, headcount, trend by experience)
2. **Where is it concentrated?** (department, job role, salary slab, age group, gender)
3. **What factors go along with leaving?** (overtime, travel, job satisfaction, marital status)

The result is a single-page dashboard that HR managers can read in under a minute and filter further for detail.

> 📄 **Dashboard preview:** [View the full dashboard (PDF)](dashboard/HR%20Analytics%20Dashboard.pdf)

---

## 🗂️ Repository Structure

```
📦 hr-analytics-dashboard
 ┣ 📜 HR_Analytics.csv              # Dataset (1,417 rows × 38 columns, ";" delimited)
 ┣ 📊 HR_Analytics_Dashboard.pbix   # Power BI report (data model + visuals)
 ┣ 📁 dashboard
 ┃ ┗ 📄 HR Analytics Dashboard.pdf  # Exported dashboard view
 ┗ 📝 README.md
```

---

## 🧭 What's Inside the Dashboard

The report (titled **"HR ANALYTICS DASHBOARD"**) has one page with 6 KPI cards and 7 charts.

### KPI Cards

| KPI | What it tells you | Value |
|---|---|---|
| 👥 **Total Employees** | Full headcount in the dataset | **1,417** |
| ✅ **Active Employees** | Employees who stayed | **1,186** |
| 🚪 **Attrition Count** | Employees who left | **231** |
| 📉 **Attrition Rate %** | Attrition ÷ total employees | **16.3%** |
| 🎂 **Average Age** | Mean age of the workforce | **36.9 years** |
| 🏢 **Avg Experience** | Mean tenure at the company | **7.0 years** |

### Visuals

| Visual | Type | Question it answers |
|---|---|---|
| Attrition by Department | Donut chart | Which department loses the most people? |
| Attrition by Salary Slab | Clustered bar | Does pay level relate to leaving? |
| Attrition by Job Role & Job Satisfaction | Matrix | Which roles combine low satisfaction with high attrition? |
| Age Group Distribution | Column chart | How is the workforce spread across age bands? |
| Attrition by Gender | Pie chart | Is attrition balanced between men and women? |
| Attrition Trend by Experience | Area chart | At which career stage do people leave? |
| Department-Wise Employee Count | Funnel | How large is each department? |

---

## 🔍 Key Insights

Figures below are calculated directly from `HR_Analytics.csv`. Attrition rate = employees who left ÷ employees in that group.

### 1. Overtime is the strongest warning sign
| Overtime | Employees | Attrition rate |
|---|---|---|
| Yes | 406 | **31.5%** |
| No | 1,011 | 10.2% |

Employees working overtime leave at roughly **3× the rate** of those who don't.

### 2. Young and newly hired employees are the flight risk
| Age group | Employees | Attrition rate |
|---|---|---|
| **18–25** | 117 | **37.6%** |
| 26–35 | 588 | 18.9% |
| 55+ | 44 | 18.2% |
| 46–55 | 222 | 12.2% |
| 36–45 | 446 | 9.2% |

Leavers are younger on average (33.8 vs 37.6 years) and have shorter tenure (5.1 vs 7.4 years). Grouping employees by years at the company shows the same pattern:

| Years at company | Employees | Attrition rate |
|---|---|---|
| 0–2 | 324 | **30.2%** |
| 3–5 | 421 | 14.5% |
| 6–10 | 436 | 12.2% |
| 10+ | 236 | 8.1% |

### 3. Attrition is not evenly spread across departments
| Department | Employees | Attrition rate |
|---|---|---|
| Sales | 207 | **25.1%** |
| Human Resources | 39 | **23.1%** |
| Administration | 406 | 20.7% |
| IT | 166 | 18.1% |
| Marketing | 64 | 15.6% |
| Finance | 23 | 13.0% |
| Operations | 512 | 8.4% |

Note that Human Resources, Finance and Marketing are small groups, so their percentages move a lot with only a few exits.

### 4. Role matters
- **Sales Representative** has the highest attrition at **41.0%** (83 employees), followed by Laboratory Technician (23.9%) and Human Resources (23.5%).
- **Research Director** (2.6%), **Manager** (5.0%) and **Manufacturing Director** (6.4%) are the most stable roles.

### 5. Other patterns worth noting
- ✈️ **Frequent travellers** leave at 25.8%, versus 8.1% for those who don't travel.
- 😐 **Low job satisfaction** (rating 1) goes with 23.0% attrition, versus 11.2% at rating 4.
- ⚖️ **Work-life balance** rated 1 goes with 31.6% attrition, though only 79 employees gave that rating.
- 💍 **Single employees** leave at 22.0%, versus 11.4% for married employees.
- 🚻 **Gender:** men 17.2% vs women 15.0%.
- 💰 **Salary slab:** attrition is highest in the **10+ LPA** group (19.8%) and ranges from 14.3% to 16.9% in the other slabs, so pay level alone does not explain leaving in this dataset.

### 💡 Recommendations for HR

1. **Review overtime workloads**, especially in Sales and for younger staff.
2. **Strengthen onboarding and career paths for the 18–25 group** and for employees in their first two years.
3. **Look into the Sales Representative role** (targets, incentives, management support).
4. **Track job satisfaction** as an early-warning metric and act on low scores.
5. **Revisit travel policy** for roles that travel frequently.

---

## 🧾 Data Dictionary

The dataset has **38 columns**. The main ones:

| Group | Columns |
|---|---|
| **Identity** | `EmpID`, `EmployeeNumber` |
| **Demographics** | `Age`, `AgeGroup`*, `Gender`, `MaritalStatus`, `Education`, `EducationField` |
| **Job** | `Department`, `JobRole`, `JobLevel`, `BusinessTravel`, `DistanceFromHome(KM)`, `OverTime` |
| **Compensation** | `MonthlyIncome`, `SalarySlab`*, `DailyRate`, `HourlyRate`, `SalaryHike %`, `StockOptionLevel` |
| **Experience** | `TotalExperience(Years)`, `NumCompaniesWorked`, `YearsatCompany`, `YearsinCurrentRole`, `YearsSincePromotion`, `YearsWithCurrManager`, `TrainingsLastYear` |
| **Satisfaction (1–4 scale)** | `EnvironmentSatisfaction`, `JobSatisfaction`, `RelationshipSatisfaction`, `JobInvolvement`, `WorkLifeBalance`, `PerformanceRating` (3–4 only) |
| **Target** | `Attrition` (Yes/No), `AttritionCount`* (1/0, used for aggregations in Power BI) |
| **Constants** | `EmployeeCount`, `Over18`, `StandardWorkingHours` (same value in every row) |

\* *Derived columns: `AgeGroup` is grouped from `Age`, `SalarySlab` from annualised `MonthlyIncome` (in LPA), and `AttritionCount` from `Attrition`.*

---

## 🛠️ Tools & Skills Demonstrated

- **Power BI Desktop:** data modelling, DAX measures (e.g. *Attrition Rate %*), interactive visuals
- **Data storytelling:** KPI cards, drill-down by department, role and demographics
- **HR analytics:** attrition drivers, workforce segmentation

---

## 🚀 How to Use

1. **Clone or download** this repository.
2. Install [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free, Windows).
3. Open `HR_Analytics_Dashboard.pbix`.
4. If Power BI shows a data-source error, or the numbers differ from this README, go to **Home → Transform data → Data source settings → Change Source**, point it to your local `HR_Analytics.csv`, then click **Refresh**. The file uses a **semicolon (`;`)** delimiter.
5. Click any chart element to cross-filter the whole report.

---

## ⚠️ Data Notes & Limitations

Being transparent about the data makes the analysis more credible:

- **14 EmpID values appear twice** (1,403 unique IDs across 1,417 rows), although no row is a full duplicate. Worth checking before any production use.
- `EmployeeCount`, `Over18` and `StandardWorkingHours` are constants and add no analytical value.
- `HourlyRate` and `MonthlyIncome` values look unrealistic (for example, hourly rate exceeds daily rate in 1,389 of 1,417 rows, and monthly income is almost unrelated to job level), which suggests the compensation fields are **synthetic or anonymised**. Treat salary-related findings as illustrative.
- `MaritalStatus` has only two categories (Single, Married), and group sizes for some departments are small.
- The analysis is **descriptive**: it shows associations, not proof of cause and effect.

---

## 📚 Data Source

The dataset follows the structure of public HR-analytics datasets on Kaggle (such as the *HR Analytics Dataset* used in Power BI tutorials, and the IBM HR Attrition dataset). This copy has been adapted (for example, `DistanceFromHome(KM)`, `SalarySlab` in LPA, and `AttritionCount`). Please credit the original dataset authors if you reuse it.

---

## 👤 Author

**Ashafa Multazam**
📧 [multazam.ashafa@gmail.com](mailto:multazam.ashafa@gmail.com) · 💼 [LinkedIn](https://linkedin.com/in/ashafamultazam) · 🐙 [GitHub](https://github.com/ashafamultazam)

⭐ If you found this project useful, please give it a star!
