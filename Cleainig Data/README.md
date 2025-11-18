# 🎬 Analytics - IMDB Movie Dataset
## ✨ Excel & Google Sheets Implementation

**Key Tools:** ⚙️ Microsoft Excel & Google Sheets

---

### 📊 1. Project Overview

This project demonstrates an **end-to-end Data Quality Control (DQC)** workflow, transforming raw, complex IMDB data into actionable insights ready for **business intelligence** and operational reporting.

**Value Proposition:** Built a framework for **Data Validation** and **KPI Calculations** directly in spreadsheets, reducing the risk of **Garbage In, Garbage Out (GIGO)** and ensuring **real-time, accurate insights**.

---

### 🛠️ 2. DQC Methodology & Key Formulas

The methodology is organized into three levels of complexity, showcasing skills from **basic cleansing** to **predictive, formula-driven analysis**.

#### A. Level 1: Data Cleansing & Standardization (Essential)
Focus on handling missing values, duplicates, and standardizing basic formats.

| # | DQC Pillar | Excel/Sheets Formula | Professional Logic & Impact |
|:-:|:---|:---|:---|
| 1 | **Handle Null Values** | `=IF(ISBLANK(E2), "N/A", E2)` | **Fill Gaps:** Replace empty cells (Duration) with marker. **Impact:** Prevents calculation errors, ensures **data completeness**. |
| 2 | **Duplicate Control** | `=IF(COUNTIF(A$2:A2, A2)>1, "DUPLICATE", "UNIQUE")` | **Data Integrity:** Flags duplicates based on **IMDB ID**. **Impact:** Produces a **unique dataset** for valid statistical analysis. |
| 3 | **Text Normalization** | `=PROPER(TRIM(B2))` | **Consistency:** Removes extra spaces and standardizes capitalization. **Impact:** Groups identical strings (e.g., Genres) correctly. |
| 4 | **Data Type Transformation** | `=DATEVALUE(C2)` | **Analysis Ready:** Converts text dates to serial **Date values**. **Impact:** Enables **time-series analysis**. |

---

#### B. Level 2: Quality Validation & Conditional Metrics (Advanced)
Focus on strong error handling, logical range validation, and preliminary KPI calculations.

| # | DQC Pillar | Excel/Sheets Formula | Professional Logic & Impact |
|:-:|:---|:---|:---|
| 5 | **Range Validation (Outliers)** | `=IF(AND(L2>=1, L2<=10), "VALID", "REVIEW")` | Ensures `Score` (L) is within 1-10. **Impact:** Isolates **outliers** affecting averages. |
| 6 | **Advanced Error Handling** | `=IFERROR(VLOOKUP(A2, Sheet2!A:B, 2, FALSE), "NOT FOUND")` | Safely merges data and replaces `#N/A` errors. **Impact:** Improves **readability** and data integrity. |
| 7 | **Cross-Column Validation** | `=AND(ISNUMBER(K2), ISBLANK(J2))` | Checks logical completeness: `Income` must be numeric AND `Director` not blank. **Impact:** Flags incomplete yet logically required data. |
| 8 | **Basic KPI Calculation** | `=AVERAGEIF(F:F, "USA", K:K)` | Computes **Average Revenue** for films in the USA. **Impact:** Provides accurate **regional performance metrics**. |

---

#### C. Level 3: Operational Analysis & Automation
Focus on **dynamic reporting**, **in-cell visualization**, and **time-based calculations**.

| # | DQC Pillar | Excel/Sheets Formula | Professional Logic & Impact |
|:-:|:---|:---|:---|
| 9 | **Dynamic Performance Analysis** | `=SUMIFS(K:K, F:F, "USA", C:C, ">"&YEAR(TODAY())-5)` | Calculates total `Income` for USA films in the **last 5 years**. **Impact:** Supports **investment decisions** with up-to-date trends. |
| 10 | **In-Cell Data Visualization** | `=REPT("█", ROUND(L2, 0))` | Creates **text-based sparkline bars** for `Score`. **Impact:** Enables quick **QA review** without charts. |
| 11 | **Ranking & Top Performer Identification** | Excel: `=RANK.EQ(K2, K:K, 0)` <br> Sheets: `=INDEX(FILTER(B:B, K:K=MAX(K:K)), 1, 1)` | Automates **rankings** and identifies **top-grossing films**. **Impact:** Supports **report automation** and discovery of positive outliers. |

---

### 🚀 3. Conclusion & Value Proposition

This DQC framework demonstrates the ability to:

1. **Build Robust Frameworks:** Design workflows that ensure **data quality and validity** end-to-end.
2. **Enable Fast Operational Insights:** Use conditional formulas and aggregation to produce **dynamic KPIs** without complex BI tools.
3. **Prepare Analysis-Ready Data:** Deliver validated datasets ready for advanced analytics, accelerating **time-to-insight (TTI)**.
