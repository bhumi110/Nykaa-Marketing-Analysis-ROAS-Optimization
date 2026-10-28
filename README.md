# Nykaa Marketing Campaign Performance & ROAS Optimization

*An end-to-end marketing analytics project using Python, Excel, and Power BI*

## Disclaimer

This project uses a publicly available marketing campaign dataset associated with Nykaa for educational and portfolio purposes. The dashboard is an independent analysis and does not represent an official Nykaa analytics report. The findings reflect the provided dataset and its calculated metrics; they should not be interpreted as verified internal company performance.

## Project Overview

This project focuses on analyzing marketing campaign performance and identifying opportunities to improve advertising efficiency. Using campaign-level data, I developed an interactive Power BI dashboard to track revenue, conversions, clicks, campaign spend, conversion rates, and Return on Ad Spend (ROAS).

The workflow involved preparing and analyzing the dataset in Python, calculating marketing performance metrics, and presenting the results through an interactive Power BI report designed to support data-driven campaign decisions.

## My Thinking Process

I approached this project from a marketing analytics perspective: businesses need to understand not only how much revenue their campaigns generate, but also how efficiently their marketing spend converts into results.

Rather than presenting revenue alone, I included funnel metrics, campaign comparisons, monthly trends, and customer-segment analysis. This makes it easier to examine campaign performance from multiple perspectives and identify areas that may require further investigation.

---

## Business Problem

Marketing teams need a clear view of which campaigns perform well, how efficiently campaign spend generates revenue, and where conversion opportunities may exist.

Without a consolidated performance dashboard, comparing campaigns across time and customer segments can be difficult. The objective of this project was to organize campaign data into an interactive report that helps identify performance differences and supports more informed marketing decisions.

## Business Questions Answered

- How much revenue, campaign spend, and how many conversions do campaigns generate?
- Which campaign types deliver stronger revenue relative to campaign spend?
- How do revenue and campaign spend change month by month?
- What proportion of impressions becomes clicks, leads, and conversions?
- Which customer segments have higher conversion rates?
- Which campaign areas should be investigated for potential optimization?

## Key Findings

- **Overall ROAS is approximately 2.95×:** The current KPI indicates about ₹2.95 in revenue per ₹1 of recorded campaign spend, subject to validating the measure and cost definition.
- **Campaign performance varies:** The ROAS chart ranks SEO and Email highest, followed by Paid Ads, Influencer, and Social Media. Recheck these values against the shared ROAS measure before treating the ranking as final.
- **Conversion rate is 22.03%:** This is the overall rate displayed on your dashboard, calculated as conversions divided by clicks.
- **Lead rate is 40.04%:** This is the displayed proportion of clicks that resulted in leads.
- **June shows a sharp decline:** Both revenue and campaign spend fall in June. The dataset ends on June 24, 2025, so incomplete-month data may contribute to the drop.
- **Customer segments differ in conversion rate:** College Students have the highest displayed rate at 24.53%, while Working Women have the lowest at 21.69%.

---

## Data Source

**Nykaa Campaign Data**, obtained from a public Kaggle dataset.

Dataset: [Nykaa Campaign Data CSV](https://www.kaggle.com/datasets/ishitabahamnia/nykaa-campaign-data-csv)

The processed dataset contains 55,555 rows and 26 columns, covering campaign performance measures such as impressions, clicks, leads, conversions, revenue, acquisition cost, ROI, campaign type, marketing channel, customer segment, and date.

The `Acquisition_Cost` field is described as cost per acquisition (CPA), rather than total campaign spend. Therefore, total campaign spend is calculated as:

`Total Campaign Spend = Acquisition_Cost × Conversions`

ROAS is calculated as:

`ROAS = Revenue ÷ Total Campaign Spend`

---

## Tools and Tech Stack

| Tool | Purpose in this project |
|---|---|
| Python (pandas) | Data preparation, cleaning, and creation of derived marketing metrics |
| Excel | Reviewing and storing the processed campaign dataset |
| Power BI Desktop | Interactive dashboard development and visualization |
| DAX | Calculating KPIs, campaign spend, ROAS, conversion rate, and lead rate |


## Core Concepts Demonstrated

- **Marketing Performance Analysis** — evaluating campaign results using revenue, clicks, leads, and conversions
- **ROAS Analysis** — comparing revenue against total campaign spend
- **Conversion Funnel Analysis** — examining impressions, clicks, leads, and conversions
- **Campaign Comparison** — comparing performance across campaign types
- **Customer-Segment Analysis** — identifying differences in conversion rates between audience groups
- **Time-Series Analysis** — examining monthly changes in revenue and campaign spend
- **Interactive BI Design** — using slicers, KPI cards, charts, and matrix visuals to support exploration

---

## Project Workflow

**Step 1 — Business Problem Definition.** Identified the need to compare campaign performance, measure revenue relative to spend, and understand conversion differences.

**Step 2 — Python Data Preparation.** Worked with the campaign dataset and prepared derived metrics, including click-through rate, lead rate, conversion rate, cost per click, cost per conversion, and revenue-to-cost ratio.

**Step 3 — Marketing Metric Calculation.** Used the dataset's CPA definition to calculate total campaign spend as acquisition cost multiplied by conversions. Calculated ROAS by dividing total revenue by total campaign spend.

**Step 4 — Power BI Dashboard Development.** Built an interactive report with headline KPIs, campaign-type comparisons, monthly trends, conversion-rate analysis by customer segment, and a campaign performance matrix.

**Step 5 — Validation.** Compared the displayed KPIs and campaign-level metrics and identified a discrepancy between the ROAS chart and matrix that needs to be resolved before publishing final campaign rankings.

---

## Dashboard Structure

**Page 1 — Home:** project branding, navigation to the two analytical pages, and a glossary of marketing metrics including CTR, conversion rate, ROAS, CPA, and ad spend.

**Page 2 — Marketing Performance Overview:** total revenue, total conversions, total clicks, and CTR as headline KPIs. Includes a monthly revenue trend, revenue by campaign type, and a funnel comparing impressions, clicks, leads, and conversions.

**Page 3 — ROAS Optimization:** ROAS, total campaign spend, cost per conversion, conversion rate, and lead rate as headline KPIs. Includes ROAS by campaign type, monthly revenue versus campaign spend, top channel combinations by conversion rate, conversion rate by customer segment, and a campaign comparison matrix.

---

## Sample DAX: Total Campaign Spend

```dax
Total Campaign Spend =
SUMX(
    CampaignData,
    CampaignData[Acquisition_Cost] *
    CampaignData[Conversions]
)
```

## Sample DAX: ROAS

```dax
ROAS =
DIVIDE(
    [Total Revenue],
    [Total Campaign Spend],
    0
)
```

## Sample DAX: Conversion Rate

```dax
Conversion Rate % =
DIVIDE(
    [Total Conversions],
    [Total Clicks],
    0
)
```

Format the conversion-rate measure as a percentage in Power BI.
