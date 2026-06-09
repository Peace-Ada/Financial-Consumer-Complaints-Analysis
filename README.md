# FINANCIAL CONSUMER COMPLAINTS ANALYSIS
---

# Table of Contents
---
- [Analysis Overview](#analysis-overview)
- [Data Source](#data-source)
- [Tools Used](#tools-used)
- [Data Cleaning & Preparation](#data-cleaning--preparation)
- [Skills Demonstrated](#skills-demonstrated)
- [Insights](#insights)
- [KPI Overview](#kpi-overview)
- [Recommendations](#recommendations)
- [Dashboard](#dashboard)
- [Conclusion](#conclusion)

---

## Analysis Overview
---
Financial institutions receive thousands of consumer complaints every year — 
but without proper analysis, these complaints are just noise. This project 
analyses 75,513 consumer complaints submitted to the CFPB (Consumer Financial 
Protection Bureau) between December 2011 and October 2020 to uncover which 
products, states, and processes were generating the most pressure on support 
teams — and why.

Key questions answered include:
- Which financial products generate the most complaints?
- Which states are most affected and why?
- What is causing delays in complaint responses?
- Why are customers still disputing after receiving a response?
- What response type is most effective at preventing disputes?

---

## Data Source
---
- **Dataset:** CFPB Consumer Complaint Database
- **Source:** Kaggle
- **Size:** 75,513 records
- **Period:** December 2011 – October 2020
- **Fields include:** Product, Sub-product, Issue, Sub-issue, 
  Consumer complaint narrative, Company response, State, 
  Submitted via, Date received, Date sent to company

![Dataset preview — attach your image here]

---

## Tools Used
---
- **Microsoft Excel:** Primary tool for data cleaning, 
  analysis and dashboard development
- **Pivot Tables:** Used to aggregate and summarise 
  complaint volumes by product, state, response type 
  and time period
- **Power Query:** Used for data transformation, 
  standardisation and column formatting
- **Excel Charts & Slicers:** Used to build two 
  interactive dashboards with dynamic filtering

---


## Data Cleaning & Preparation
---
The dataset came as 3 separate sheets - Complaints,
Products and Issues. Before any analysis could begin,
these had to be merged and cleaned into one reliable
working table.

**Step 1 — Inspected the raw dataset**

Loaded and reviewed all 3 sheets to understand the
structure and identify relationships between tables.
The Complaints sheet contained Product IDs and Issue
IDs as codes not readable names  which meant the
Products and Issues sheets needed to be joined before
analysis could begin.

![Raw dataset showing 3 separate sheets](images/complaint_raw_data.png)

---

**Step 2 — Merged 3 sheets using XLOOKUP**

Used XLOOKUP to pull Product Names, Sub Products,
Issue Names and Sub Issues from the Products and
Issues sheets directly into the Complaints sheet
creating one unified readable table.

Formula used:
![XLOOKUP formula merging sheets](images/complaint_xlookup_formula.png)

![Merged table — all 3 sheets combined](images/complaint_merged_tables.png)

---

**Step 3 — Handled missing values and blanks**

Several columns contained blank entries particularly
in Tags, Consumer Consent Provided and Company Public
Response fields. Each blank was assessed based on
whether the column was required for analysis.

![Missing values identified across key columns](images/complaint_missing_valuesblanks.png)

---

**Step 4 — Created calculated columns**

New columns were created to support deeper analysis:
- **Complaint Intake Lag (Days)** — calculated as
  the difference between Date Submitted and Date
  Received to measure how long each complaint took
  to enter the system
- **Year** — extracted from Date Received for
  year-over-year trend analysis

Formula used:
![Calculated columns — Intake Lag and Year](images/complaint_calculated_column.png)

---

**Step 5 — Built Pivot Tables for analysis**

Created multiple Pivot Tables to answer specific
business questions including submission channel
impact on intake speed and response strategy
effectiveness in preventing disputes.

![Pivot tables — channel lag and response effectiveness](images/complaint_pivot_tables.png)


## Skills Demonstrated
---
- Data Cleaning & Preparation in Excel and Power Query
- Pivot Table Development and Aggregation
- Calculated Column Creation
- Year-over-Year Comparative Analysis
- Root Cause Analysis using the 5-Why Framework
- Interactive Dashboard Design with Slicers
- Data Storytelling and Business Recommendation Writing
- Time-Series and Trend Analysis
---

## KPI Overview
---

![KPIs 1](images/complaintkpi1.png)

![KPIs 2](images/complaintkpi2.png)

The KPI cards show the following:

- **Total Complaints:** 75,513  
- **Top Complaint Product:** Credit Card *(19,176 | 25.4% of total complaints)*  
- **Average Monthly Complaints:** 6,293  
- **On-Time Response Rate:** 98%  
- **Total Disputes Filed:** 7,363 *(10% dispute rate)*
- **Year-over-Year Complaint Change:** -4% in 2020 vs 2019

 ---

## Insights

---

### Insight 1 — Credit cards drive 25.4% of all complaints and 50% of all disputes

Out of 75,513 total complaints, credit cards alone 
account for 19,176. But the bigger problem is what 
happens after: of the 7,363 disputes filed across 
all products, 3,696 (50%) came specifically from 
credit card resolutions. Even after customers 
received a response, half of credit card complainants 
were still not satisfied. The specific pain points 
are billing disputes (3,203 cases) and APR/interest 
rate issues (1,704 cases).

![Complaints by product chart](images/complaint1.png)

**Key Takeaway:**
The problem is not the product itself — it is 
specifically how billing disputes and interest rate 
issues are being handled and communicated to customers.

---

### Insight 2 — 4 states generate 41% of all national complaints

California (12,107), New York, Florida, and Texas 
together account for over 31,000 of the 75,513 total 
complaints. These are the highest-population states 
with the most active financial product users. Within 
each of these states, credit cards rank #1 and 
mortgages rank #2 in California and New York specifically.

![Complaints by state map](images/complaint%20b.png)

**Key Takeaway:**
Support capacity allocated to these states does not 
reflect the actual complaint concentration. A 
one-size-fits-all staffing model is failing the 
highest-volume regions.

---

### Insight 3 — Delays are a process failure, not a staffing problem

1,469 complaints (2%) received untimely responses. 
Bank account and checking/savings products account 
for 59.9% of all delays. The root cause is the 
absence of pre-approved resolution workflows for 
the most common delay-causing issues: managing an 
account (291 delays), deposits and withdrawals (267), 
and low funds issues (125). Every case is being 
treated from scratch.

![Delay analysis chart](images/complaint3.png)

**Key Takeaway:**
Building structured resolution workflows for these 
specific complaint types would eliminate the majority 
of the delay problem without adding headcount.

---

### Insight 4 — Explanations prevent disputes but quality is the missing piece

Closed with explanation covers 64.81% of all 
resolutions and is the most effective dispute 
prevention tool in the data. However 10% of 
customers are still disputing even after receiving 
a closed with explanation response — which means 
the explanations themselves are not meeting the 
standard required to fully resolve the complaint.

![Response type breakdown](images/complaint4.png)

**Key Takeaway:**
Improving explanation quality and response templates 
specifically for credit card resolutions would 
directly lower the 10% dispute rate without 
additional cost.

---

## Recommendations
---

**Immediate (0–30 days)**
- Replace email complaint intake with a structured 
  web form. Email averages a 5.99-day intake lag 
  vs web at 1.32 days
- Set a 3-day maximum SLA for referral complaints

**Short-Term (1–3 months)**
- Design pre-approved resolution workflows for 
  managing an account and deposits/withdrawals 
  complaint types
- Scale support capacity in California, New York, 
  Florida and Texas to match actual complaint load

**Quality Improvement**
- Rewrite credit card response templates especially 
  for billing disputes and APR issues
- Track dispute rate monthly to measure improvement

**Long-Term (3–6 months)**
- Build an early-warning system that flags any 
  product with a month-over-month complaint spike 
  above 15%
- Introduce seasonal staffing pre-plans for the 
  June–September peak period

---

## Dashboard
---
Two interactive dashboards were built in Excel — 
Dashboard 1 covers complaint trends and product/state 
breakdowns. Dashboard 2 focuses on operational 
performance including response delays, dispute rates 
and intake channel analysis.

![Dashboard 1 — Complaint Trends and Overview](images/complaint-dashboard1.png)

![Dashboard 2 — Operational Performance and Response Analysis](images/complaint-dashboard2.png)

---

## Conclusion
---
This analysis of 75,513 financial consumer complaints 
reveals that the problem is not random — it is 
concentrated, predictable and fixable. Credit cards 
are the dominant complaint driver. Four states 
generate nearly half of all national complaints. 
Delays are caused by missing workflows, not missing 
staff. And disputes persist because explanation 
quality is inconsistent.

The recommendations provided give financial 
institutions a clear, structured path to reducing 
complaint volumes, improving response times and 
cutting dispute rates — all without requiring 
significant new investment.

Data does not lie. It just needs someone willing 
to listen to it.

---

Thank you for reading!

Let's connect:
LinkedIn: [Peace Adaobi](https://www.linkedin.com/in/peace-ada-95b341341)  
Email: [peaceada100@gmail.com](mailto:peaceada100@gmail.com)
