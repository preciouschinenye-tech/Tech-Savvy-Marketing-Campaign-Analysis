# Tech Savvy Solutions: Q3 Marketing Campaign Performance Analysis
An Excel analysis of 30 marketing campaigns (July to September 2024) that answers one business question: where should the marketing budget go next quarter?

The project covers data cleaning, KPI reporting, a dashboard, channel and campaign analysis, correlation, segmentation and a simple Q4 projection. It also records the data problems I found and how much they change the conclusions.

**Marketing Performance Dashboard**

An Excel dashboard was developed to provide a consolidated view of campaign performance.

The dashboard provides a visual summary of Q3 marketing campaign performance, including revenue, advertising spend, ROI, leads, and conversions.

![Marketing Performance Dashboard](04_Image/Marketing_Dashboard.png)

### Project at a Glance

| Item | Details |
|---|---|
| **Programme** | Skill2Scale 4-Week Virtual Internship (Data Analytics), Cohort 6 |
| **Client (scenario)** | Tech Savvy Solutions, a fictional digital marketing consultancy for e-commerce brands |
| **Period analysed** | Q3 2024 (July to September) |
| **Data** | 30 campaigns after cleaning (32 raw rows, 2 duplicates removed), 15 raw columns |
| **Currency** | Nigerian naira (₦) |
| **Tool** | Microsoft Excel 2016 (Pivot Tables, Pivot Charts, formulas, dashboard) |
| **Analyst** | Precious Onyedum |

### Business problem

The marketing manager wanted to know:

- Which campaigns and channels returned the most for the money spent?
- Does spending more on advertising bring more leads?
- How did performance change across the quarter?
- Which campaigns should be scaled, fixed or reviewed in Q4?

##### Headline Numbers

| KPI | Value | How it is calculated |
|---|---|---|
| Total revenue | ₦68,770,000 | Sum of campaign revenue |
| Total ad spend | ₦11,495,000 | Sum of campaign ad spend (see data limits below) |
| Leads / conversions | 8,003 / 1,835 | Sum across campaigns |
| Conversion rate | 22.93% | Conversions ÷ leads |
| Cost per lead | ₦1,436 | Total ad spend ÷ total leads |
| Cost per conversion | ₦6,264 | Total ad spend ÷ total conversions |
| Average campaign ROI | 471% | Simple mean of the 30 campaign ROIs |
| Median campaign ROI | 344% | The middle campaign, less affected by extreme values |
| Overall ROI | 498% | (Total revenue − total spend) ÷ total spend |
| Click-through rate | 2.25% | Indicative only, see limitations |

**ROI** is calculated as (Revenue − Ad Spend) ÷ Ad Spend. The Week 4 client brief asks for total campaign ROI, which is the overall figure (498%). The 471% average is shown for comparison.

### Key findings

1. **Paid Ads earned the most revenue, but not the best return.** It brought in ₦17.63M (25.6% of revenue) while using 39.4% of the ad spend. Its ROI is about 289%. Email (about 538%) and Display (about 565%) returned more for each naira spent.
2. **The Referral Programme and the segmented VIP email campaign had the highest ROI.** Referral turned ₦250,000 of spend into ₦8.0M of revenue (3,100% ROI). The VIP email campaign turned ₦85,000 into ₦1.98M (2,229% ROI). Both are small, single campaigns, so they need testing before anyone assumes they will scale.
3. **Audio Ads was the weakest channel with complete data.** It used 5.9% of ad spend (₦680,000) but produced only 2.0% of revenue (₦1.4M), an ROI of about 106%. Organic and Messaging only look weak in the original pivot because they have no ad spend recorded, so their ROI shows as 0%.
4. **Revenue depends heavily on a few campaigns.** Three campaigns that ran for the whole quarter (Referral Programme, Display Ads Q3 and SEO Content Push) produced ₦18.56M, which is 27% of total revenue.
5. **More spend does not guarantee more leads.** The correlation between ad spend and leads is 0.45 (R² ≈ 0.20), so spend explains about one fifth of the variation in leads. It rises to 0.57 if the three zero-spend rows are removed. Targeting, creative and channel clearly matter too.
6. **Campaign segments:** 20 campaigns (67%) were High Performers (ROI of 300% or more), 4 (13%) were Average (100% to 299%) and 6 (20%) were Low (below 100%). Read the Low group with care, because some of those six are data problems, not poor campaigns (see below).
7. **Revenue by launch month fell from ₦34.44M in July to ₦18.04M in August and ₦16.29M in September.** This pattern is largely caused by how revenue is assigned to months, so do not read it as a real collapse (see below).

### Recommendations

1. **Test a budget shift before scaling.** Keep Paid Ads running, but move a small share of its budget (for example 10% to 15%) to Email and Display for one campaign cycle and compare ROI.
2. **Test whether Referral and segmented email can grow. Both returned a lot from very small budgets.** Increase spend step by step and watch whether ROI holds.
3. **Review only the genuinely weak campaigns.** Audio Ads is the weakest channel with complete data (about 106% ROI). Radio Digital Ad (57%) and Instagram Summer (87%) are the only campaigns with both spend and revenue recorded that returned less than 100%.
4. **Fix how data is recorded.** Mark missing ad spend as "not reported", not zero. Record revenue by the month it was earned. Use the standard campaign template described in the Business Optimisation Proposal.

### Data source and quality

**Source.** The data comes from the Skill2Scale virtual internship, which is a guided simulation with a fictional client. The brief describes the dataset as "messy" on purpose, so that cleaning could be practised, and the competitor data could be "public or simulated". The figures are training data, not real company performance, and I could not verify how they were produced. Treat the results as a demonstration of method.

### Limitations: how much to trust the results

I reviewed the finished analysis again and found the following issues. They do not make the project worthless, but they change how some numbers should be read.

| Issue | What happened | Effect on the results |
|---|---|---|
| Months are based on launch date | Each campaign's full revenue is placed in the month it started. Three campaigns that ran all quarter (₦18.56M) are all counted in July. | Without them, July is ₦15.88M, August ₦18.04M and September ₦16.29M, which is roughly flat. The 47.6% "fall" and the Q4 decline projection are therefore mostly a result of the method. |
| Missing spend was set to ₦0 | LinkedIn B2B Push (spend blank) and WhatsApp Campaign (spend "N/A") became ₦0 spend, and SEO Content Push genuinely had ₦0. All three show 0% ROI and are labelled Low Performers, yet they earned ₦8.4M (12% of revenue). | Their true ROI is unknown for the first two, so the Low Performer group and the "bottom 3" list overstate weak performance. Total spend is probably understated, and overall ROI probably overstated. |
| Revenue "-" set to ₦0 | End of Q3 Social was still "Pending" and its revenue was recorded as "-". It appears as -100% ROI. | This shows missing revenue, not proven failure. |
| Click values were replaced | 17 raw rows had the identical value 2,340 in the Clicks column. In the cleaned data, 16 were replaced with values equal to 2% or 3% of impressions. Referral's missing impressions were set to 0. | The 2.25% CTR is partly built on assumptions. Treat it as indicative and do not base decisions on it. |
| Averages are skewed | Referral (3,100%) and VIP email (2,229%) pull the average ROI up. | The median (344%) describes a typical campaign better than the 471% average. |
| Small sample | Only 30 campaigns, and some channels (Referral, Organic, Messaging, Affiliate) are a single campaign. | Channel ROI for those channels is really one campaign's ROI. |
| Correlation, not cause | The 0.45 correlation comes from 30 data points. | It shows an association only. |
| Q4 projection is very simple | The forecast applies the average of only two monthly growth rates (-47.6% and -9.7%) to three future months. | Use it to show the method, not to plan a budget. |
| Competitor comparison is simulated | The brief allowed public or simulated competitor data. The BrandPulse NG and AdVance Digital figures are illustrative. | They are not real benchmarks, so they are not used in the findings above. |

### Project Workflow

**1. Data Cleaning steps and Preparation**

The raw dataset was reviewed and prepared for analysis.

Key activities included:

- Removed 2 duplicate rows (C001 and C003), leaving 30 campaigns.
- Standardised text formats (for example "completed" and "Completed") and dates.
- Replaced "N/A" and blank ad spend with 0, and an invalid "-" revenue value with 0.
- Corrected one row where values had shifted into the wrong column.
- Recalculated ROI for every campaign because some values were missing.
- Added Month (based on campaign start date) and Segment (based on ROI).
- Replaced missing account managers with "Unknown - Pending Confirmation".

A cleaned dataset was prepared for subsequent analysis.

**2. Exploratory Data Analysis**

Descriptive analysis was conducted to understand the overall distribution and performance of the marketing campaigns.

Key metrics examined included:

- Total Revenue
- Total Advertising Spend
- Average ROI
- Total Leads
- Total Conversions
- Conversion Rate

**4. Monthly Trend Analysis**

Campaign performance was grouped into July, August, and September to examine changes across the Q3 reporting period.

The analysis considered:

- Monthly revenue
- Monthly advertising spend
- Average monthly ROI
- Monthly leads
- Monthly conversions

**5. Correlation Analysis**

The Excel CORREL function was used to examine the relationship between advertising spend and leads generated.

A scatter plot with a linear trendline and R-squared value was used to visualise the relationship.

This analysis helps assess whether higher advertising expenditure was associated with increased lead generation.

**6. Campaign Segmentation**

Campaigns were classified using ROI-based performance thresholds:

| Segment	| ROI Threshold |
|---|---|
| High Performer	| 300% and above |
| Average Performer	| 100% – 299% |
| Low Performer	| Below 100% |

This classification provides a structured way to compare campaigns and identify those requiring further review.

**7. Q4 Revenue Projection**

Q4 revenue projections were developed using the average month-over-month growth rate observed during Q3.

The projection covers:

- October
- November
- December

**Forecast assumption:** The projection assumes that the average Q3 month-over-month growth rate continues throughout Q4, with no significant changes in market conditions, marketing strategy, or business operations.

The projections are estimates, not guaranteed revenue outcomes.

**8. Competitor Benchmarking**

A competitor comparison matrix was developed to compare Tech Savvy Solutions with two simulated competitors:

- BrandPulse NG
- AdVance Digital

The comparison considered ROI, cost per lead, marketing channel, conversion rate, and revenue.

Competitor figures are illustrative and were created for the purpose of the portfolio exercise. They should not be interpreted as verified market data.

## Key Business Questions

The analysis was designed to answer the following questions:

1. Which campaigns generated the highest and lowest ROI during Q3?
2. Which marketing channels generated the most revenue?
3. Which channels delivered stronger returns relative to their performance?
4. How did marketing performance change between July and September?
5. Is there a relationship between advertising expenditure and lead generation?
6. Which campaigns should receive further investment, optimisation, or review?
7. What revenue could the business potentially generate during Q4 if the observed growth pattern continues?
8. How does Tech Savvy Solutions compare with the simulated competitors?

###  Project Brief and Deliverables

The work follows the four weekly client briefs from the programme. Each week built on the one before.

| Week | Brief | What I delivered | Where to find it |
|---|---|---|---|
| 1 | Data foundations | Cleaned dataset, data dictionary, folder SOP, summary statistics, data summary email | Workbook sheets (Cleaned Data, Data Dictionary, Folder Structure SOP, Summary Statistics); `Week_1_Data_Summary_Email.pdf` |
| 2 | Visualisation and insight | Dashboard with 5 KPIs, pivot tables, insights report, executive summary | `Marketing_Dashboard.png`; `Week_2_Performance_Insights_Report.pdf`; `Pivot_Table.pdf` |
| 3 | Business intelligence and prediction | Monthly trend, correlation, segmentation, Q4 projection, competitor comparison, strategy memo | `Week_3_Business_Intelligence_Report.pdf`; `Strategic_Recommendation_Memo.pdf` |
| 4 | Executive reporting | End-of-month analytics report, optimisation proposal, portfolio presentation, reflection | `Final_Analytics_Report.pdf`; `Business_Optimisation_Proposal_Memo.pdf`; `Portfolio_Presentation.pptx`; `Personal_Reflection.pdf` |

## Skills demonstrated

- **Data cleaning:** duplicate removal, missing-value handling, format standardisation, recalculating ROI
- **Analysis:** ROI, conversion rate, cost per lead, correlation (CORREL), segmentation, month-over-month growth
- **Excel:** Pivot Tables, Pivot Charts, slicers, KPI dashboard
- **Business communication:** reports, memos and recommendations written for a marketing manager
- **Critical review:** finding and documenting data limitations that affect the conclusions

## Project Structure

```text
Tech-Savvy-Marketing-Campaign-Analysis/
│
├── Excel_Workbook/
│   └── Tech_Savvy_Marketing_Analysis.xlsx
│
├── Reports/
│   ├── Week_1_Email.pdf
│   ├── Week_2_Insights_Report.pdf
│   ├── Week_3_Business_Intelligence_Report.pdf
|   ├── Pivot_Table.pdf
│   ├── Final_Analytics_Report.pdf
│   ├── Business_Optimisation_Proposal.pdf
│   ├── Strategic_ Recommendation_Memo.pdf
│   └── Personal_Reflection.pdf
│
├── Presentation/
│   └── Portfolio_Presentation.pptx
│
├── Images/
│   └── Marketing_Dashboard.png
│
└── README.md
```
**Workbook sheets:** Raw Data, Cleaned Data, Summary Statistics, Data Dictionary, Folder Structure SOP and Pivot Tables.

### Conclusion

This project demonstrates how Microsoft Excel can be used to transform raw marketing campaign data into meaningful business insights.

By combining data cleaning, exploratory analysis, dashboard development, campaign segmentation, correlation analysis, forecasting, and competitor benchmarking, the project provides a structured approach to evaluating marketing performance.

Beyond reporting historical results, the analysis focuses on helping decision-makers understand what is working, identify areas requiring improvement, and make more informed marketing investment decisions.
