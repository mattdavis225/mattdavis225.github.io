---
layout: default
title: Transportation Cost Forecasting Project
---

# OM 621: Advanced Visual Analytics - Course Project Repository

This repository contains all analysis and deliverables for **OM 621: Advanced Visual Analytics** course assignments.

The central project (Assignments 1, 2, and 3) is a consulting case focused on developing a **Transportation Cost Estimation and Forecasting System** for a client facing significant challenges due to delayed shipment invoicing.



https://github.com/user-attachments/assets/2eca6411-647d-4f6e-bd1c-523e47df31b5



## Project Overview

**Core Problem**  
A significant delay (weeks to months) exists between the time a shipment is sent and when the company receives the carrier invoice. This creates high uncertainty in budgeting, forecasting, and accurate cost allocation across divisions.

**Dataset Used**  
Fictitious historical data from the dataset entitled `tr_data_22_24` (and `tr_23_24` for detailed analysis).

**Solution**  
A proactive forecasting and visualization system that leverages historical patterns, seasonality, transportation mode differences, and delay characteristics to provide accurate cost estimates before invoices arrive.

---

## Assignment 1: Context and Storytelling

### The Case: Transportation Cost Estimation and Forecasting

**Client Scenario**  
You are a consultant assisting the Director of Supply Chain at **ODW Logistics** with transportation cost challenges, specifically **outbound transportation for E.L.F. Cosmetics shipments** to customers (primarily Walmart).

### Audience
- **Primary**: Michael Dixon – Director of Supply Chain Management, ODW Logistics (Ontario, California)
- **Secondary**: 
  - Michael Dixon’s direct reports (analysts, senior program managers, data engineers)
  - Consulting firm management (project overseer)

### Core Challenge
Significant delay (weeks to months) in receiving invoices for outbound transportation creates high uncertainty in budgeting, forecasting, and cost allocation across divisions.

### Solution Approach
1. **Data Request & Cleaning** – Two years of historical shipment and invoice data  
2. **Data Analysis & Feature Engineering** – Created a "delay" feature (`invoice_date - shipping_date`)  
3. **Information Visualization** – Boxplots, time-series, density plots to reveal patterns and seasonality  
4. **Estimation & Forecasting System** – Proactive cost estimation dashboard providing visibility into expected costs before invoices arrive

### Revised 3-Minute Story (for Michael Dixon & Team)

> "Good morning, Michael, and team. I’m here today as a consultant brought in by E.L.F. Cosmetics to address a challenge that is critical to your financial planning: the uncertainty of transportation costs. We're specifically focusing on your outbound shipment modes for E.L.F. product moving through ODW Logistics to your key customer.
>
> As you know, there is often a significant delay—sometimes weeks or months—between the time a shipment leaves the dock and when ODW Logistics receives the carrier's invoice for that transportation. Right now, this lag is making it hard to accurately forecast and budget for transportation costs, hindering your ability to efficiently allocate costs by division.
>
> We’ve analyzed two years of your historical shipping and invoicing data, engineering a crucial 'delay' variable. Our analysis has confirmed that this delay is highly variable, often exceeding 90 days, and is significantly related to the mode of transportation used. For instance, certain modes like container loads show the longest invoice delays, and the data suggests a link between the length of the delay and the final invoice amount. Furthermore, our time series analysis reveals clear seasonal peaks in invoice totals, indicating periods where proactive budget planning is even more essential.
>
> We are not here to micro-manage the warehouse floor or the 3PL's operations. Our successful solution is a comprehensive **cost estimation and forecasting system**. This system will leverage the identified trends and seasonality to predict future transportation costs with greater accuracy and bring instant visibility to the expected cost of shipments before the invoice even arrives. This proactive approach will transform your budgeting process from a reactive scramble to a strategic advantage. It will allow you to allocate resources effectively and maintain financial control throughout the year.
>
> The next step is to demonstrate this system, starting with the Power BI dashboard, and discuss how we integrate this into your existing planning cycle."

### Storyboard Outline
1. **The Challenge** – Timeline showing shipment → delay gap → invoice (cost known)
2. **Audience & Scope** – Focus on E.L.F. outbound, led by Michael Dixon; key modes (truck, air, container)
3. **Data Discovery** – Historical shipments/invoices + engineered DELAY variable
4. **Delay Patterns** – Boxplot of delay by mode (ordered largest → smallest delay)
5. **Cost Trends** – Upward growth + strong Q4 seasonality, December dip
6. **Mode-Specific Forecasting** – Faceted/small multiples showing different trends/seasonality per mode
7. **The Solution & Impact** – Concept of Power BI dashboard: estimated vs actual cost + budgeting accuracy metrics

---

## Assignments 2 & 3: Key Findings and Accomplishments

### Dataset: `tr_23_24`
Key columns:
- `site` – Manufacturing site (e.g., US77, TH2E, CH22)
- `mode` – Transportation mode:
  - `exp_air`, `std_air`, `full_container_load`, `less_container_load`, `truck_load`, `less_truck_load`, `parcel_grund`, `parcel_air`, `other`
- `region` – AMER, APAC, EMEA
- `destination`, `shipping_date`, `invoice_date`, `usda_invoice_amount`

### Data Quality Summary
| Column              | Non-null Count | Null Count | % Null     |
|---------------------|----------------|------------|------------|
| site                | 200,549        | 8,250      | 4.1%       |
| mode                | 208,157        | 642        | 0.3%       |
| division            | 185,843        | 22,956     | 12.3%      |
| region              | 208,799        | 0          | 0%         |
| destination         | 208,799        | 0          | 0%         |
| shipping_date       | 208,799        | 0          | 0%         |
| invoice_date        | 208,799        | 0          | 0%         |
| usda_invoice_amount | 208,799        | 0          | 0%         |

**Invoice Amount Statistics**  
- Average: $12,779  
- Minimum: $0.007612  
- Maximum: $192,806

### Key Insights from Assignment 2 (Delay Analysis)

- **Site US77** dominates activity (54.6% of shipments)
- **Region AMER** accounts for the vast majority of shipments
- **Most common modes**: Less Than Truckload (LTL) ~20.2%, Truckload (TL) ~20.1%
- **Least common**: Parcel Air and Parcel Ground (~0.24% each)
- Delays vary significantly by **site** and **mode**:
  - US sites (US77, US62): shorter delays (~19 days mean)
  - Overseas sites (TH2E, CH22, NL6F): longer delays (~26–27 days) with heavier tails
- Positive correlation between delay length and invoice amount (stronger in US sites)
- **Container modes (especially LCL)** have the longest and most variable delays (median ~60 days for LCL, tails to 120+ days)
- **Parcel modes** have near-instant invoicing (~1 day)

**Key Visualization**: Boxplot of delay by mode (ordered descending) clearly highlights container modes as high-risk for budgeting uncertainty.

### Key Insights from Assignment 3 (Time Series & Forecasting)

- Strong **seasonality** across nearly all modes: sharp increase through fall, peak in November, drop in December
- Clear **year-over-year growth** in many modes, but varies significantly:
  | Mode                  | Trend vs Overall | Seasonality Notes                                      | Year-over-Year Growth |
  |-----------------------|------------------|--------------------------------------------------------|------------------------|
  | exp_air               | Similar          | Pronounced Q4 peak, 2024 dips mid-year                 | Yes                   |
  | full_container_load   | Different        | 2022 had early surge; 2023–2024 more gradual          | Weak/unclear          |
  | less_container_load   | Similar          | Strong Q4 seasonality                                 | Yes                   |
  | less_truck_load       | Slightly diff    | Moderate growth, variable peak months                  | Yes (moderate)        |
  | parcel_air            | Very different   | Highly volatile, mid-year spikes                       | Irregular             |
  | parcel_ground         | Different        | Volatile upward trend, no consistent YoY growth        | Weak                  |
  | std_air               | Similar shape    | Steady climb, flat YoY growth                          | Minimal               |
  | truck_load            | Similar          | Consistent YoY growth, milder seasonality than LTL    | Yes                   |





**Final Deliverable**: A Power BI-based **Transportation Cost Estimation and Forecasting System** that provides proactive visibility and significantly improves budgeting accuracy.

---
