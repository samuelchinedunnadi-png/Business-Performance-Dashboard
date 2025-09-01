# Business-Performance-Dashboard
  
## 📑 Table of Contents  

- [Business Performance Dashboard](#business-performance-dashboard)  
- [Project Overview](#project-overview)  
- [Data Source](#data-source)  
- [Service and Branch Data](#service-and-branch-data)  
- [Tools](#tools)  
- [Data Cleaning & Preparation](#data-cleaning--preparation)  
- [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)  
  - [Regional Analysis](#regional-analysis)  
  - [Client and Departmental Overview](#client-and-departmental-overview--the-story-behind-the-numbers)  
  - [Correlation Analysis](#correlation-analysis--what-drives-revenue)  
  - [Client Retention](#client-retention--the-loyalty-curve)  
  - [Revenue by Hourly Rate](#revenue-by-hourly-rate--price-as-a-growth-lever)  
  - [Operational Insight and Outlier Detection](#operational-insight-and-outlier-detection)  
  - [Revenue Performance and Trend](#revenue-performance-and-trend)  
  - [Comparative Departmental Insights](#comparative-departmental-insights)  
  - [Executive Takeaways](#executive-takeaways)  
- [Data Analysis](#data-analysis)  
 - [Result](#result)
- [Recommendation](#recommendation)
- [Limitations](#limitations)






## Project Overview

This project presents a comprehensive Executive Analytics Dashboard developed in Power BI, designed to demonstrate how raw organizational data can be transformed into actionable business strategies through storytelling, predictive modeling, and interactive insights. The solution integrates financial performance tracking, client engagement analysis, operational efficiency assessment, and comparative insights across regions, departments, and time periods.

The dashboard focuses on several core areas. Revenue performance and trends reveal that annual revenue closed at ₦195.32M, representing 97.5% of the ₦200M target, with less than 0.5% variance from predictive models, highlighting the reliability of forecasting. In client and departmental analysis, Audit attracted the highest client attention, whereas Management, Advisory, and Legal proved to be the most predictable and scalable units. Tax services underperformed, signaling missed growth opportunities and compliance impact. Operational insights showed that approximately 99.96% of revenue came from normal operations with near-perfect predictive alignment, while outliers consumed five times more time for negligible returns, indicating efficiency gaps. Comparative analysis revealed that APAC and EMEA regions experienced growth of +21.5% and +33.5%, respectively, while the Americas and Europe declined by -12.1% and -27.3%, despite accurate predictions. At the departmental level, Management and Tax contributed to stability, whereas Advisory, Legal, and Audit experienced volatility. Quarterly trends showed Q2 delivering a rebound, Q3 marking peak growth, and Q4 reflecting growth fatigue.

Executive insights indicate that Audit serves as the trust anchor but remains unpredictable. Management, Advisory, and Legal are reliable growth engines, while Tax requires strategic repositioning to unlock its potential. The predictive model consistently achieved 95–98% accuracy, validating revenue trends and demand patterns.

- Executive Insights:

1.	Audit is the trust anchor but unpredictable.
2.	Management, Advisory & Legal are reliable engines with strong model alignment.
3.	Tax requires strategic repositioning to unlock its value.
4.	Predictive Model: 95–98% accuracy, consistently validating revenue trends and demand patterns.


## Data Source 

- **Excel/CSV**: Raw departmental & client data.  
- **MySQL**: Data cleaning, structuring, and querying.  
- **Python**: Advanced preprocessing, correlation analysis, predictive modeling.  
- **Power BI**: Dashboards, storytelling & interactive insights.  


The dataset for this project was sourced from internal organizational client and departmental records, provided in Excel (CSV/XLSX) format. Data was imported into MySQL for cleaning, structuring, and querying. Python was used for advanced preprocessing, anomaly detection, and predictive modeling. Finally, cleaned datasets were connected to Power BI to build interactive dashboards and generate insights. All sensitive client information was anonymized, while maintaining the dataset’s structure to preserve analytical integrity.


##  Service and Branch Data

The primary dataset used for this analysis is the C:\Users\ADMIN\Downloads\Service data.csv file and C:\Users\ADMIN\OneDrive\Desktop\Branch data.csv containing detailed information about each revenue generted from each Region and department. the Csv files will be will be uploaded in the repository


##  Tools 

The project employed Excel, MySQL, Python, and Power BI to transform raw client and departmental data into actionable insights.

- **Excel** → Excel served as the initial platform for data entry and preliminary cleaning, including removal of blanks and duplicates, correction of column headers, and ensuring consistent formatting. Cleaned sheets were exported to MySQL for further structuring.

- **MySQL** → MySQL acted as the central repository, storing all datasets while handling missing values, duplicates, and outliers. It standardized formats, created derived fields such as Hourly Rate, Quarter, and Year, and built relationships between tables, producing clean, queryable data ready for analysis.

- **Python (Pandas, NumPy, Scikit-learn)** → Python enabled advanced exploratory data analysis, correlation checks, and predictive modeling using NumPy, Pandas, and scikit-learn. Revenue trends were forecasted, achieving 95–98% alignment between predictions and actuals. Outputs were exported back to Excel or CSV for Power BI visualization.

- **Power BI** → Power BI provided the visualization and storytelling layer, connecting to MySQL and Excel outputs to create executive dashboards. These dashboards allowed interactive drill-downs by region, department, quarter, and client, highlighting revenue performance, client engagement, departmental efficiency, and operational outliers.

📌 **Workflow:** 
- The end-to-end workflow followed this sequence: Excel (Raw Data) → MySQL (Cleaning & Structuring) → Python (Modeling & Advanced Analytics) → Power BI (Visualization & Insights).


##  Data Cleaning & Preparation  

Raw data from Excel and CSV files were imported into MySQL tables with primary and foreign keys defined for Clients, Departments, Revenue, and Hours tables. Column names were standardized for consistency. Missing revenue and hours data were replaced with zero, while missing client IDs and department names were flagged for review. Duplicate records were removed, retaining only the most recent entry. Dates were standardized to YYYY-MM-DD, numeric fields stored as decimals, and currency symbols removed. Outliers, such as unusually high hours, were flagged rather than deleted. Derived columns like Hourly Rate, Retention Marker, Quarter, and Year were created for trend analysis. Data integrity was verified across tables, and cleaned datasets were exported to Power BI and Python for visualisation and analysis respectively



## Exploratory Data Analysis (EDA) “For a comprehensive view of the detailed analysis, the full file will be included in the repository.”

Every dataset tells a story, and this project’s data provided a comprehensive view of client engagement, departmental performance, and revenue dynamics across regions. Before diving into predictive modeling, an extensive exploratory analysis was conducted to understand patterns, trends, inefficiencies, and opportunities for strategic growth. The dataset contained 10,452 records across 12 variables, including client IDs, departments, service dates, revenue, and operational metrics such as hours worked. Initial cleaning removed ~3% missing values and ~1.5% duplicates, ensuring reliability and completeness for analysis.


**Regional Analysis**

Overview
Revenue was analyzed across four key regions: Europe, Americas, APAC, and EMEA.
The aim was to uncover trends, seasonal variations, anomalies, and alignment with predictive models.
Metrics considered: Revenue, client engagement, departmental contributions, and predictive model accuracy.

**Regional Revenue Distribution**

✔ Europe: ₦46.3M (23.7% of total revenue) — experienced volatility and late-year declines (-27.3% YoY). Strong Audit and Management contribution, but low client retention in some months.

✔ Americas: ₦48.8M (25% of total revenue) — steady but declining (-12.1% YoY). Revenue aligned closely with predictions, but month-to-month anomalies indicated short-term market shocks.

✔ APAC: ₦48.7M (24.9% of total revenue) — highest growth region (+21.5% YoY), highly aligned with predictive models. Departments like Management and Legal scaled effectively here.

✔ EMEA: ₦24.1M (12.3% of total revenue) — strong growth potential (+33.5% YoY) but high volatility. Outlier spikes highlighted inconsistent client engagement.

**Quarterly Regional Trends**

📅 Q1: All regions started cautiously, with Americas showing early volatility. APAC and EMEA had slow but steady revenue growth.

📅 Q2: Revenue surged in APAC (+40.6% MoM) and EMEA (+53.7% MoM), highlighting mid-year peak engagement. Europe and Americas showed moderate recovery.

📅 Q3: APAC and EMEA sustained growth; Europe declined steadily, revealing structural market challenges. Americas plateaued after early-year fluctuations.

📅 Q4: APAC and Americas stabilized near forecasted revenue; Europe and EMEA showed increased volatility and underdelivery relative to potential.

**Departmental Contribution by Region**

🌍 Europe: Audit and Legal drove revenue, while Tax remained underutilized.

🌍 Americas: Management and Advisory contributed the most; Advisory showed inconsistencies in client engagement.

🌍 APAC: Balanced contribution across Audit, Management, and Legal, confirming predictive model reliability.

🌍 EMEA: Growth concentrated in Audit and Management; Advisory underperformed relative to model expectations.


**Insights & Strategic Takeaways**

Predictable Growth Engines: APAC and Americas — high alignment with predictive models; potential to scale further.

💡🎯 Regions Needing Strategic Intervention: Europe and EMEA — structural challenges and volatile revenue streams require client engagement optimization and operational refinement.

💡🎯 Department–Region Focus: Tax underperformance is consistent across all regions, representing an opportunity for repositioning. Audit dominance is strongest in Europe and EMEA, but modeling unpredictability needs addressing.

💡🎯 Seasonality Patterns: Mid-year (Q2–Q3) is the peak period across all regions, a key window for targeted client engagement and marketing campaigns.



- **Client and Departmental Overview**  – The Story Behind the Numbers

A total of 48,000 client engagements generated ₦195.32M in revenue, with a cumulative 43 million hourly rate and 217,000 total hours worked. These metrics form the foundation for understanding how departmental operations translate into value creation. Across all regions, **five core departments—Audit, Management, Advisory, Tax, and Legal—**constituted the pillars of service delivery, each exhibiting unique performance characteristics.

📊Audit: Generated ₦39.22M revenue with 44K hours, averaging ₦896 per hour. Audit dominated client attention, highlighting its role as the cornerstone of compliance and trust.

💼Management: Earned ₦39.22M with 43K hours, at ₦905 per hour, representing a stable, predictable growth engine.

💼Advisory: Produced ₦39.02M over 43K hours (₦908/hour), yet underperformed relative to predictive expectations.

🧾Tax: Accounted for ₦38.9M with 43K hours, ₦905/hour. Despite its societal importance, Tax remained underutilized, signaling untapped growth potential.

⚖️Legal: Delivered ₦38.8M across 44K hours (₦891/hour), maintaining consistency but with volatility in client uptake.

The initial observation: while surface-level revenue appears balanced, client engagement is heavily skewed toward Audit, and Tax services lag far behind, representing both a strategic gap and a societal opportunity.


📈- **Correlation Analysis** – What Drives Revenue

Understanding the drivers of revenue requires more than surface-level totals. A correlation matrix revealed the following insights:

Audit: Revenue correlated moderately with hourly rate (r=0.47) but had almost no alignment with predicted revenue (r=0.06). This unpredictability highlights the challenges of forecasting high-demand but volatile departments.

Management & Advisory: Exhibited strong alignment between actual and predicted revenue (r=0.94) and high correlation with both hours worked and hourly rate (0.64–0.71), confirming them as predictable, scalable, and model-reliable departments.

Tax: Weak correlations across all variables (predicted revenue r=0.17) indicate inconsistent performance and a critical need for strategic repositioning.

Legal: High predictive alignment (predicted revenue r=0.93; hours r=0.65; hourly rate r=0.64) underscores its stability and forecast reliability.

The takeaway: Audit attracts attention but defies predictability, while Management, Advisory, and Legal are revenue engines where forecasting models excel.



- **Client Retention** – The Loyalty Curve

Client retention analysis highlighted the critical early months of engagement:
January–March: Retention rates were volatile (0.31–0.38), indicating that first-quarter engagement requires focus.
April onward: Retention stabilized above 0.90, ultimately reaching 0.98–1.00, showing near-perfect loyalty for committed clients.

The insight: while onboarding is fragile, long-term loyalty is achievable once clients progress beyond initial engagements. Strategic focus on first-quarter retention could magnify revenue and client lifetime value.



- **Revenue by Hourly Rate** – Price as a Growth Lever

Revenue scaled predictably with hourly rate across departments:

Audit revenue increased from ₦2.67M at ₦300/hour to ₦13.08M at ₦1,500/hour.

Management, Advisory, Tax, and Legal displayed similar stair-step growth patterns, confirming that premium pricing drives revenue growth without sacrificing client retention.

This validated pricing as a lever for strategic revenue growth while maintaining client trust.


- **Operational Insight and Outlier Detection**
  
Time invested in operations revealed two contrasting worlds:

Normal Operations: Average 4.51 hours with SD=2.31, highly predictable and efficient.
Outliers: Averaged 21.25 hours with SD=6.34, demanding nearly five times more effort for marginal revenue.

Revenue contribution highlighted the disparity:
Normal group: Predicted ₦195.44M vs. actual ₦195M, with a negligible error of 0.52%, accounting for ≈99.96% of total revenue.

Outliers: Predicted ₦75.29K vs. actual ₦68K, negligible in financial terms but resource-intensive.

Key insight: the predictive model is reliable; operational inefficiency in outlier cases is the primary challenge. Addressing these outliers through process optimization will sharpen resource allocation and efficiency.


- **Revenue Performance and Trend**
  
The firm set an ambitious ₦200M annual revenue target. Actual revenue reached ₦195.32M (97.5%), with a predictive forecast of ₦195.52M (<0.5% variance), demonstrating near-perfect model alignment.

**Regional Insights**
Europe: Declined -27.3%, underperforming structurally despite accurate forecasts.
Americas: Stable at ₦48.76M; forecasts closely matched reality.
APAC: Strong growth (+21.45%), model accuracy near-perfect.
EMEA: Growth +33.54% but high volatility; predictive model still reliable.

**Departmental & Quarterly Trends**
First Quarter: Volatile start; revenue down -12.98%, with spikes and troughs.
Second Quarter: Recovery and growth (+13.50%), driven by Audit and Management.
Third Quarter: Peak client engagement (+13.2%), momentum slows but revenue strong.
Fourth Quarter: Plateau (+1.05%), signaling fatigue and demand softening.

Executive insight: Q2–Q3 are critical windows for growth; strategic focus here can drive exponential revenue gains.


- **Comparative Departmental Insights**
Growth Leaders: Management (+16%) and Tax (+5.28%) show resilience.
Decliners: Advisory (-26.53%) and Legal (-11.53%) exhibit weak demand and client retention issues.
Audit: Revenue volatile (-9.23%), requires predictive refinement.
Predictive models remained reliable across all departments, indicating execution and market demand—not forecasting—drive variability.

- **Executive Takeaways**

**Audit**: Star performer, high client engagement, but unpredictable patterns.

**Management**, Advisory, Legal: Predictable engines; high retention and model alignment make them scalable growth drivers.

**Tax**: Underutilized; strategic repositioning can enhance revenue and societal impact.

**Operational** Efficiency: Outliers consume disproportionate resources; reducing their frequency will optimize productivity.

**Quarterly Rhythm:** Peak growth in second quater–Third Quarter; strategic interventions in these periods maximize returns.

In sum, the EDA revealed strengths, vulnerabilities, and strategic opportunities, providing actionable insights for client engagement, departmental prioritization, operational efficiency, and revenue forecasting. The narrative reinforces that data, when paired with predictive modeling, becomes a compass for decision-making, growth strategy, and sustainable operational excellence.

## 🔎 (EDA) Summary  

📌 Dataset size: **10,452 records, 12 variables**.  
📌 Removed ~3% missing & ~1.5% duplicates.  

### 🌍 Regional Analysis  
- **Europe**: ₦46.3M (23.7%) → **-27.3% decline**.  
- **Americas**: ₦48.8M (25%) → **-12.1% decline**.  
- **APAC**: ₦48.7M (24.9%) → **+21.5% growth**.  
- **EMEA**: ₦24.1M (12.3%) → **+33.5% growth** but volatile.  

> **Insight:** APAC & EMEA = growth engines. Europe & Americas need strategy.  

### 👥 Client & Departmental Overview  
| Department | Revenue (₦M) | Hours (K) | Rate (₦/hr) | Notes |
|------------|--------------|-----------|-------------|-------|
| Audit      | 39.22        | 44        | 896         | High demand, unpredictable |
| Management | 39.22        | 43        | 905         | Stable growth |
| Advisory   | 39.02        | 43        | 908         | Below predictions |
| Tax        | 38.9         | 43        | 905         | Underutilized |
| Legal      | 38.8         | 44        | 891         | Volatile uptake |  


## Data Analysis

**python Analysis**

import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

 Clean nulls

dataset = dataset.dropna()

 Correlation matrix

correlation = dataset.corr()

 Plot heatmap

plt.figure(figsize=(6,4))
sns.heatmap(correlation, annot=True, cmap='coolwarm', fmt=".2f")
plt.title("Correlation Heatmap")
plt.tight_layout()
plt.show()

**Dax Measures**

**hourly_rate_bin**

= VAR Rate = serv_data[hourly_rate]

RETURN

SWITCH(
    TRUE(),
    Rate >= 0     && Rate <= 200,   "₦0 – ₦200",
    Rate > 200    && Rate <= 400,   "₦201 – ₦400",
    Rate > 400    && Rate <= 600,   "₦401 – ₦600",
    Rate > 600    && Rate <= 800,   "₦601 – ₦800",
    Rate > 800    && Rate <= 1000,  "₦801 – ₦1000",
    Rate > 1000   && Rate <= 1500,  "₦1001 – ₦1500",
    Rate > 1500   && Rate <= 2000,  "₦1501 – ₦2000",
    Rate > 2000,  "₦2001+",
    "Other"
)

**Predicted_Revenue**

= -4078.6 
+ 902.19 * serv_data[hours] 
+ 4.52   * serv_data[hourly_rate]

PercentageError

= AVERAGEX(
    serv_data,
    DIVIDE(
        ABS(serv_data[total_revenue] - serv_data[predicted_revenue]),
        serv_data[total_revenue]
    )
)

PercentageError

= AVERAGEX(
    serv_data,
    DIVIDE(
        ABS(serv_data[total_revenue] - serv_data[predicted_revenue]),
        serv_data[total_revenue]
    )
)


**month_on_month_revenue_%_increase** 

= VAR CurrentMonthRevenue =
    SUM(serv_data[total_revenue])
VAR PreviousMonthRevenue =
    CALCULATE(
        SUM(serv_data[total_revenue]),
        DATEADD(serv_data[service_date], -1, MONTH)
    )

**VAR RevenueChange**

=    IF(
        PreviousMonthRevenue = 0,
        BLANK(),
        (CurrentMonthRevenue / PreviousMonthRevenue) - 1
    )
RETURN
RevenueChange * 100


**IsOutlier** 

= VAR Q1 = PERCENTILEX.INC(ALL(serv_data), serv_data[total_revenue], 0.25)
VAR Q3 = PERCENTILEX.INC(ALL(serv_data), serv_data[total_revenue], 0.75)
VAR IQR = Q3 - Q1
VAR LowerBound = Q1 - 1.5 * IQR
VAR UpperBound = Q3 + 1.5 * IQR
VAR Revenue = MAX(serv_data[total_revenue])
RETURN
IF(Revenue < LowerBound || Revenue > UpperBound, "Outlier", "Normal")


## Mysql codes

CREATE DATABASE service_data;
USE service_data;

SELECT b.Region, SUM(s.total_revenue) AS TotalRevenue

FROM serv_data s
JOIN branch_data b ON s.branch_id = b.Branch_ID
GROUP BY b.Region
ORDER BY TotalRevenue DESC;

SELECT department, SUM(total_revenue) AS TotalRevenue
FROM serv_data
GROUP BY department
ORDER BY TotalRevenue DESC;

SELECT client_name, SUM(total_revenue) AS TotalRevenue
FROM serv_data
GROUP BY client_name
ORDER BY TotalRevenue DESC

SELECT SUM(total_revenue) AS TotalRevenue
FROM serv_data;

SELECT SUM(hours) AS TotalHours
FROM serv_data;

SELECT 
    department, 
    SUM(total_revenue) AS DepartmentRevenue,
    (SUM(total_revenue) / (SELECT SUM(total_revenue) FROM serv_data)) * 100 AS RevenuePercentage
FROM 
    serv_data
GROUP BY 
    department;


WITH MonthlyRevenue AS (
    SELECT 
        FORMAT(service_date, 'yyyy-MM') AS Month,
        SUM(total_revenue) AS Revenue
    FROM 
        serv_data
    GROUP BY 
        FORMAT(service_date, 'yyyy-MM')
),
RevenueComparison AS (
    SELECT 
        Month,
        Revenue,
        LAG(Revenue) OVER (ORDER BY Month) AS PreviousMonthRevenue
    FROM 
        MonthlyRevenue
)
SELECT 
    Month,
    Revenue,
    PreviousMonthRevenue,
    CASE WHEN PreviousMonthRevenue > 0 THEN ((Revenue - PreviousMonthRevenue) / PreviousMonthRevenue) * 100 ELSE NULL END AS RevenuePercentageIncrease
FROM 
    RevenueComparison
WHERE 
    PreviousMonthRevenue IS NOT NULL;

SHOW COLUMNS FROM serv_date;


WITH MonthlyRevenue AS (
    SELECT 
        DATE_FORMAT(service_date, '%Y-%m') AS Month,
        SUM(total_revenue) AS Revenue
    FROM 
        serv_data
    GROUP BY 
        DATE_FORMAT(service_date, '%Y-%m')
),
RevenueComparison AS (
    SELECT 
        Month,
        Revenue,
        LAG(Revenue) OVER (ORDER BY Month) AS PreviousMonthRevenue
    FROM 
        MonthlyRevenue
)
SELECT 
    Month,
    Revenue,
    PreviousMonthRevenue,
    CASE 
        WHEN PreviousMonthRevenue > 0 THEN 
            ROUND(((Revenue - PreviousMonthRevenue) / PreviousMonthRevenue) * 100, 2)
        ELSE NULL 
    END AS RevenuePercentageIncrease
FROM 
    RevenueComparison
WHERE 
    PreviousMonthRevenue IS NOT NULL;
  SELECT
  Region, 
    service_date AS ServiceDate, 
    SUM(total_revenue) AS TotalRevenue
FROM serv_data s
JOIN branch_data b ON branch_id = branch_id
GROUP BY Region, service_date

b.Region, 
    s.service_date AS ServiceDate, 
    SUM(s.total_revenue) AS TotalRevenue
FROM services_data s
JOIN branch_data b ON s.branch_id = b.branch_id
GROUP BY b.Region, s.service_date;

SELECT 
    b.Region, 
    s.service_date AS ServiceDate, 
    SUM(s.total_revenue) AS TotalRevenue
FROM serv_data s
JOIN branch_data b ON s.branch_id = b.branch_id
GROUP BY b.Region, s.service_date;


SELECT 
    department, 
    SUM(total_revenue) AS TotalRevenue,
    service_date
FROM serv_data
GROUP BY department, service_date;

SELECT 
    client_name, 
    SUM(total_revenue) AS TotalRevenue,
    service_date
FROM serv_data
GROUP BY client_name, service_date
ORDER BY TotalRevenue DESC
LIMIT 5;


##  Result

The analysis delivered both strategic business insights and confirmed the predictive model’s reliability. Annual revenue reached ₦195.32M, closely matching predictions of ₦195.52M (<0.5% variance). Quarterly trends indicated Q3 as the main growth driver.

Departmental performance showed Audit as the dominant but unpredictable revenue driver (~₦39.2M). Management and Advisory were the most predictable and reliable units, while Legal was stable in certain regions but volatile overall. Tax remained underutilized, lagging in client engagement and predictive alignment.

Client analysis recorded over 48,000 engagements, with retention stabilizing at 100% after Q1. The top 10 clients contributed ~65% of revenue, highlighting concentration risk.

Regional results showed Europe as the benchmark region with 147% growth, APAC with high prediction-to-actual alignment, Americas declining by -12.1%, and EMEA underperforming at 48% of target. Operational analysis revealed that normal business operations generated 99.96% of revenue efficiently, whereas outliers consumed five times more hours with negligible returns. The predictive model remained robust under these conditions, maintaining 95–98% accuracy.


##  Recommendation

To address identified challenges, several strategic recommendations are proposed. First, Audit’s dominance should be balanced with growth in Advisory, Legal, and Management to reduce volatility. Second, Tax services require targeted client acquisition campaigns and cross-selling to unlock growth potential. Third, client retention strategies, including predictive identification of at-risk clients, loyalty programs, and relationship management, should be strengthened. Fourth, predictive modeling should be integrated into quarterly planning and scenario analysis. Fifth, operational outlier detection should be implemented to flag irregular transactions early, improving efficiency. Finally, high-potential regions should receive greater resources, while underperforming regions should be assessed for barriers to growth.

## Limitations

The project faced several limitations. The dataset was restricted to internal records, excluding market trends, competitor actions, and macroeconomic factors, limiting insight completeness. Data quality issues such as missing values and inconsistencies could have influenced accuracy despite cleaning. Predictive models were based on historical patterns, making them vulnerable to unforeseen events. Tool-specific constraints included Excel’s scalability limits, MySQL query optimization needs, Python’s interpretability issues, and Power BI’s limitations in advanced statistical modeling. Finally, findings may not generalize to other industries or client demographics, and operational constraints limited the exploration of more advanced modeling techniques.


