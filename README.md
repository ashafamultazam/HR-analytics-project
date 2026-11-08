<div align="center">

# 📊 HR Analytics Dashboard

### Who is leaving, why, and what can HR do about it?

An interactive **Power BI** dashboard that turns 1,000 employee records into a clear picture of workforce attrition.

![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Dataset](https://img.shields.io/badge/Records-1%2C000-0A66C2?style=for-the-badge)
![Columns](https://img.shields.io/badge/Features-38-2E8B57?style=for-the-badge)
![Focus](https://img.shields.io/badge/Focus-Employee%20Attrition-D9534F?style=for-the-badge)

</div>

---

## 🎯 Project Overview

Employee turnover is expensive: it means lost knowledge, recruitment costs, and lower team morale. This project analyses an HR dataset of **1,000 employees across 7 departments** to answer three practical questions:

1. **How big is the attrition problem?** (overall rate, headcount, trend by experience)
2. **Where is it concentrated?** (department, job role, salary slab, age group, gender)
3. **What factors go along with leaving?** (overtime, travel, job satisfaction, marital status)

The result is a single-page dashboard that HR managers can read in under a minute and filter further for detail.

> 📄 **Dashboard preview:** [View the full dashboard (PDF)](dashboard/HR%20Analytics%20Dashboard.pdf)

---

## 🗂️ Repository Structure

```
📦 hr-analytics-dashboard
 ┣ 📜 HR_Analytics.csv              # Raw dataset (1,000 rows × 38 columns, ";" delimited)
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
| 👥 **Total Employees** | Full headcount in the dataset | **1,000** |
| ✅ **Active Employees** | Employees who stayed | **810** |
| 🚪 **Attrition Count** | Employees who left | **190** |
| 📉 **Attrition Rate %** | Attrition ÷ total employees | **19.0%** |
| 🎂 **Average Age** | Mean age of the workforce | **36.0 years** |
| 🏢 **Avg Experience** | Mean tenure at the company | **4.5 years** |

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
| Yes | 299 | **35.8%** |
| No | 701 | 11.8% |

Employees working overtime leave at roughly **3× the rate** of those who don't.

### 2. Young employees are the flight risk
| Age group | Employees | Attrition rate |
|---|---|---|
| **18–25** | 116 | **37.9%** |
| 26–35 | 438 | 20.5% |
| 55+ | 30 | 16.7% |
| 46–55 | 138 | 13.0% |
| 36–45 | 278 | 11.9% |

Leavers are also younger on average (32.7 vs 36.7 years) and have shorter tenure (3.4 vs 4.8 years).

### 3. Attrition is not evenly spread across departments
| Department | Employees | Attrition rate |
|---|---|---|
| Human Resources | 30 | **30.0%** |
| Sales | 166 | **28.3%** |
| Administration | 322 | 22.4% |
| IT | 101 | 20.8% |
| Finance | 17 | 17.6% |
| Marketing | 35 | 14.3% |
| Operations | 329 | 10.0% |

Note that Human Resources, Finance and Marketing are small groups, so their percentages move a lot with only a few exits.

### 4. Role matters
- **Sales Representative** has the highest attrition at **42.3%** (78 employees), followed by Human Resources (28.6%) and Laboratory Technician (27.4%).
- **Research Director** (0.0%), **Manager** (4.2%) and **Manufacturing Director** (5.0%) are the most stable roles.

### 5. Other patterns worth noting
- ✈️ **Frequent travellers** leave at 30.3%, versus 10.2% for those who don't travel.
- 😐 **Low job satisfaction** (rating 1) goes with 28.0% attrition, versus 12.7% at rating 4.
- 💍 **Single employees** leave at 26.0%, versus 12.6% for married employees.
- ⚖️ **Gender:** men 20.7% vs women 16.5%.
- 💰 **Salary slab:** attrition is highest in the **10+ LPA** group (24.4%) and similar across the lower slabs (17.0% to 18.3%), so pay level alone does not explain leaving in this dataset.

### 💡 Recommendations for HR

1. **Review overtime workloads**, especially in Sales and for younger staff.
2. **Strengthen onboarding and career paths for the 18–25 group** during their first years.
3. **Look into the Sales Representative role** (targets, incentives, management support).
4. **Track job satisfaction** as an early-warning metric and act on low scores.
5. **Revisit travel policy** for roles that travel frequently.

---

## 🧾 Data Dictionary

The dataset has **38 columns**. The main ones:

| Group | Columns |
|---|---|
| **Identity** | `EmpID`, `EmployeeNumber` |
| **Demographics** | `Age`, `AgeGroup`, `Gender`, `MaritalStatus`, `Education`, `EducationField` |
| **Job** | `Department`, `JobRole`, `JobLevel`, `BusinessTravel`, `DistanceFromHome(KM)`, `OverTime` |
| **Compensation** | `MonthlyIncome`, `SalarySlab`, `DailyRate`, `HourlyRate`, `SalaryHike %`, `StockOptionLevel` |
| **Experience** | `TotalExperience(Years)`, `NumCompaniesWorked`, `YearsatCompany`, `YearsinCurrentRole`, `YearsSincePromotion`, `YearsWithCurrManager`, `TrainingsLastYear` |
| **Satisfaction (1–4 scale)** | `EnvironmentSatisfaction`, `JobSatisfaction`, `RelationshipSatisfaction`, `JobInvolvement`, `WorkLifeBalance`, `PerformanceRating` |
| **Target** | `Attrition` (Yes/No), `AttritionCount` (1/0, used for aggregations in Power BI) |
| **Constants** | `EmployeeCount`, `Over18`, `StandardWorkingHours` (same value in every row) |

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
4. If Power BI shows a data-source error, go to **Home → Transform data → Data source settings → Change Source** and point it to your local `HR_Analytics.csv`. The file uses a **semicolon (`;`)** delimiter.
5. Click any chart element to cross-filter the whole report.

---

## ⚠️ Data Notes & Limitations

Being transparent about the data makes the analysis more credible:

- **10 EmpID values appear twice** (990 unique IDs across 1,000 rows), although no row is a full duplicate. Worth checking before any production use.
- `EmployeeCount`, `Over18` and `StandardWorkingHours` are constants and add no analytical value.
- `HourlyRate` and `MonthlyIncome` values look unrealistic in places (for example, hourly rate can exceed daily rate), which suggests the compensation fields are **synthetic or anonymised**. Treat salary-related findings as illustrative.
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
