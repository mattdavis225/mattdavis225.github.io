# OM 620 – Inventory Analytics & Safety Stock Project

### California State University San Marcos  
**Course:** OM 620 – Tools & Technologies for Business Analytics  

---

## Project Overview

This project showcases my ability to work with a simulated real-world transactional datasets and perform end-to-end inventory analytics, from raw data cleaning to SKU-level safety stock calculation.

The work combines two seperate assignments (data preparation & exploratory analysis) and (statistical computation of safety stock) into a logical workflow.  

All code, commentary, and calculations are contained in a single notebook, which provides a transparent, reproducible process for anyone reviewing the project.

---

## Phase 1 — Data Cleaning & Preparation

The analysis begins with a large transactional dataset containing order quantities, lead times, manufacturing sites, SKU identifiers, and stocking policies.  

Key steps included:

### **Standardizing column names**
Ensuring consistency across the dataset for clean, error-free analysis.

### **Investigating numeric anomalies**
Using summary statistics (`describe()`) to identify:
- Negative or unrealistic values  
- Outliers  
- Unusual lead times  
- Potential data entry errors  

Each discovery is documented along with the rationale for correction or retention.

### **Handling missing values (NaNs)**
A column-by-column assessment determined:
- How many values were missing  
- Whether the pattern was random  
- The most appropriate resolution for each case  

### **Filtering for relevant SKUs**
Since safety stock applies only to **Finished Goods (FG)** in **Make-to-Stock (MTS)** environments, the dataset was filtered to include only these SKUs.

Insights gathered from the filtered set:
- Number of unique SKUs  
- Manufacturing sites supported  
- Divisions involved  
- Top/bottom transactions by order quantity  
- Top/bottom transactions by total sales value  

This phase forms the foundation for reliable safety stock modeling.

---

## Phase 2 — SKU-Level Aggregation & Demand Statistics

For each SKU meeting the FG/MTS criteria, I calculated:

- Minimum order quantity  
- Maximum order quantity  
- Mean order quantity  
- Median order quantity  
- Variance & standard deviation  
- Average lead time  

These serve as the core demand parameters supporting the safety stock calculation.

---

## Phase 3 — Safety Stock Calculation

Safety stock was computed using **two methods**:

### **Traditional Normal-Distribution Formula**
Using z-scores for  
- 75% service level  
- 90% service level  
- 95% service level  

Formula applied:

\[
\text{Safety Stock} = z \times \sigma \times \sqrt{\text{Lead Time}}
\]

This provides a statistically grounded estimate based on assumed normal demand.

### **Empirical (Quantile-Based) Method**
To avoid assumptions about demand distribution:

\[
\text{Safety Stock} = Q_{\text{service level}} - \mu
\]

This method pulls directly from historical data, offering a more flexible and realistic buffer estimate.

### Key Results:
- **Highest safety stock SKU** identified  
- **Lowest safety stock SKU** identified  
- **Average safety stock across all SKUs** computed  
- Comparison between empirical and traditional methods  

These insights support inventory policy decisions and stockout-risk mitigation.

---

## Key Learnings & Takeaways

- **Data cleaning** is essential for any downstream operational analysis.  
- **Finished Goods + MTS** filtering is crucial for meaningful safety stock calculations.  
- **SKU-level variability** drives major differences in safety stock requirements.  
- **Service level selection** dramatically impacts safety stock and inventory carrying cost.  
- **Empirical methods** offer a powerful alternative when data does not follow a normal distribution.

---

## Project Files

The full project, including code, calculations, and explanations, is available on GitHub:

**GitHub Repository:**  
https://github.com/mattdavis225/CSUSM-OM620-Projects

---

## Direct Access

The combined notebook can be viewed here:

`/notebooks/Assignment Notebook.ipynb`  


---

## Contact

If you'd like to learn more about this project or discuss analytics work:  

**Matthew Davis**  
LinkedIn: www.linkedin.com/in/matthew-davis-8b597bb8

---
