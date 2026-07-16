# 🏦 Bank Loan Analytics Dashboard
 
End-to-end loan performance analysis focusing on application trends, funding efficiency, and risk indicators to support data-driven lending decisions.
 
---
 
## 🎯 Project Overview
 
This project focuses on analyzing a bank's loan portfolio to support centralized monitoring of loan performance, portfolio quality, and cash flow. As loan application volume grows, stakeholders need a clear summary to understand the current state of the portfolio and its distribution patterns across various business dimensions.
 
A Power BI dashboard was developed as an interactive analytical solution that allows users to monitor key loan metrics, distinguish performance between good loans and bad loans, and explore application, disbursement, and repayment patterns down to the individual loan level.
 
---
 
## 🔍 Business Questions
 
- What is the overall condition of the loan portfolio in terms of application volume, funded amount, and payments received?
- What proportion of the current portfolio consists of good loans versus bad loans?
- How are loan applications distributed by time, loan purpose, region, and borrower characteristics?
- In which areas is the most loan funding disbursed and the most payments received?
- How can loan-level detail data support further investigation and validation of aggregate findings?
---
 
## 📊 Dataset Overview
 
The dataset contains bank loan data covering application information, borrower characteristics, loan status, funded amounts, payments received, and key financial metrics such as interest rate and debt-to-income ratio (DTI).
 
---
 
## 🛠️ Tools & Technologies
 
- **Microsoft Power BI Desktop** – for data modeling and interactive visualization
- **Microsoft SQL Server** – as the primary data source
- **DAX (Data Analysis Expressions)** – for KPIs, time intelligence, and custom aggregate calculations
- **Power Query** – for data cleaning and transformation
- **Many-to-One Data Relationships** – linking the main loan dataset with a date reference table for time-based analysis
---
 
## 📊 Dashboard Breakdown & Insights
 
### Summary – Portfolio Snapshot
<img width="877" height="78" alt="Screenshot 2026-07-16 100000" src="https://github.com/user-attachments/assets/a6fbed29-d995-4785-be02-10d39507095e" />

Key metrics summarizing the overall health of the loan portfolio.
 
**Insight:**
- Total loan applications recorded at **38.6K**, with a Month-to-Date increase of **4.3K** and Month-over-Month growth of **6.91%**.
- Total funded amount reached **$435.8M**, while total amount received reached **$473.1M**, indicating a larger cash inflow than the funds disbursed.
- The portfolio's average interest rate stands at **12.05%** and average DTI at **13.33%**, providing a baseline risk profile for borrowers overall.

### Summary – Good Loan vs Bad Loan
<img width="870" height="161" alt="image" src="https://github.com/user-attachments/assets/adf2e7f1-9c98-4269-aac4-aec8e21a6a9e" />

Loan quality segmentation based on loan status.
 
**Insight:**
- **86.2%** of total applications are classified as good loans (**33.2K applications**), with total funded amount of **$370.2M** and total amount received of **$435.8M**.
- **13.8%** of applications are classified as bad loans (**5.3K applications**), with funded amount of **$65.5M** and amount received of **$37.3M**.
- The gap in contribution between good and bad loans shows that portfolio performance is concentrated in the healthy loan segment.

### Summary – Loan Status Detail
<img width="868" height="169" alt="image" src="https://github.com/user-attachments/assets/fc63e914-fd42-40aa-8b1f-e4ea1ea4e2a3" />

Distribution of key metrics by loan status.
 
**Insight:**
- **Fully Paid** dominates both application volume (32,145) and total amount received ($411.59M), with the lowest average interest rate (**11.64%**) and a DTI of **13.17%**.
- **Charged Off** (5,333 applications) has an average interest rate of **13.88%** and DTI of **14.00%** — higher than Fully Paid, as expected for defaulted loans.
- **Current** (1,098 applications) actually shows the **highest average interest rate of the three (15.10%)** and DTI of **14.72%** — even higher than Charged Off, warranting continued monitoring as these loans may be at risk of shifting into default.

### Overview – Application, Funding & Repayment Patterns
Analysis of application, funding, and repayment patterns by time, loan purpose, term, region, and borrower characteristics.

<img width="701" height="256" alt="Screenshot 2026-07-16 100607" src="https://github.com/user-attachments/assets/ef08a1e8-8da7-4cbf-bbaf-3aec5ff82343" />

**Insight:**
- Application volume, funded amount, and amount received all grew consistently throughout the year (from ~2.3K in January to ~4.3K in December) — indicating steady portfolio growth rather than seasonal spikes.
- All three metrics are dominated by the **Debt Consolidation** loan purpose (18.2K applications, far above Credit Card at ~5.0K and Other at ~3.8K) and the **60-month term** (28K applications/73.2% vs. 10K/26.8% for the 36-month term) — pointing to risk concentration within a single loan profile.
- Borrowers with **10+ years** of employment length contribute the most compared to other employment-length groups, suggesting the portfolio is dominated by borrowers with a long work history — a generally more stable risk profile.
- The portfolio is also dominated by borrowers with **Mortgage** as their home ownership status, followed by **Rent**, with owned homes making up only a small share — indicating most borrowers still carry an active mortgage obligation alongside their loan.
- Geographically, **California** is by far the largest contributor to both applications and funded amount, followed at a distance by **Texas** and **New York** — indicating portfolio exposure is concentrated in a small number of states.

### Detail – Loan-Level Data
<img width="852" height="323" alt="image" src="https://github.com/user-attachments/assets/0daea5c9-010f-4017-b92c-cf89251d78c8" />

Individual loan-level view for further investigation.
 
**Insight:**
- Data is presented down to the individual loan level, including ID, loan purpose, grade, sub-grade, term, funded amount, interest rate, installment, and amount received.
- Equipped with dynamic filters (State, Grade, Good vs Bad), enabling quick exploration and validation of aggregate findings from the Summary and Overview sections without re-aggregating the data.
---
 
## 📈 Key Insights
 
- The loan portfolio is predominantly good loans (86.2%), contributing the most to funded amount and amount received.
- The **Current** status shows a higher risk profile (interest rate & DTI) than Charged Off — an early warning signal worth monitoring.
- Loan demand is highest for **Debt Consolidation** purposes and **60-month** terms, with geographic concentration in **California**.
- Borrowers with **10+ years** of employment length dominate application volume, suggesting an overall more stable borrower profile.
---
 
## 💡 Business Implications
 
- **The Current status, with the highest interest rate and DTI, deserves priority attention.** The average interest rate for Current loans (15.10%) is higher than both Charged Off (13.88%) and Fully Paid (11.64%), as is the DTI (14.72% vs. 14.00% vs. 13.17%). This pattern suggests that some active loans carry a risk profile equal to or higher than loans that have already defaulted — the collections team should prioritize monitoring Current loans with a DTI above 14%.
- **Risk is concentrated in Debt Consolidation, 60-month terms, and California.** These three dimensions consistently dominate both volume and value across the portfolio. The risk team should consider setting a separate exposure limit or monitoring process for loans combining all three characteristics, since a quality decline in this segment would have the largest impact on the overall portfolio.
- **Heavy reliance on good loans (86.2%) makes the portfolio sensitive to small shifts.** Because overall portfolio performance is heavily supported by the good loan segment, even a small decline in this segment's quality (e.g., due to macroeconomic changes) could significantly affect total amount received. A simple stress test simulating a 5–10% decline in good loans is recommended.
- **Loan-level data speeds up validation without re-analysis.** Access to individual loan-level data allows the risk/collections team to quickly investigate specific cases (e.g., loans with extreme DTI) without waiting for a new aggregate report — accelerating the operational decision-making cycle.
---
 
## 🎓 Skills Demonstrated
 
**Technical**
- Data modeling and data processing in Power BI
- DAX for KPIs, time intelligence, and aggregate calculations
- Power Query for data cleaning and transformation
- Building interactive dashboards with filters and page navigation
**Business**
- Data-driven portfolio monitoring
- Loan quality segmentation (risk profiling)
- Distribution and exposure concentration analysis
- Translating data findings into actionable business recommendations

---

## 📷 Full Dashboard Pages

A complete look at each dashboard page for quick visual reference.

<p align="center">
  <img src="https://github.com/lailabudianti/BankLoanDashboard/blob/main/Project%20Bank%20Loan_Summary.jpg?raw=true" width="70%"/>
  <img src="https://github.com/lailabudianti/BankLoanDashboard/blob/main/Project%20Bank%20Loan_Overview.jpg?raw=true" width="45%"/>
  <img src="https://github.com/lailabudianti/BankLoanDashboard/blob/main/Project%20Bank%20Loan_Detail.jpg?raw=true" width="45%"/>
</p>

---

## 🔖 Notes
 
- This project was built following a tutorial as a learning exercise, with additional exploration and insights developed independently.
- The data has been anonymized and does not represent the actual operations of any financial institution.
