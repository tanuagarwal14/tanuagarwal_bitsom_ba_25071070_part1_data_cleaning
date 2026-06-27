# Part 1: Business Data Cleaning, Validation & Excel Reporting

## Problem Summary

The objective of this assignment is to clean, validate, and prepare a retail orders dataset for business analysis. The raw dataset contains inconsistent text formatting, mixed date formats, missing values, duplicate records, invalid discounts, and order status issues. The cleaned dataset is then used to generate summary reports and pivot tables for business reporting.

---

## Dataset Description

**Dataset:** Retail Orders Dataset

**Source:** Instructor-provided dataset

**Files Used:**
- `data/raw_orders.xlsx`
- `data/cleaned_orders.xlsx`

The dataset contains order-level information such as customer details, product information, sales, profit, shipping details, payment status, and order status.

---

## Tools Used

- Microsoft Excel
- Pivot Tables
- Excel Functions
- Sorting and Filtering
- Conditional Formatting
- Visual Studio Code (README and Cleaning Log)

---

## Cleaning Steps Performed

- Preserved the original dataset without modification.
- Removed extra spaces and standardized text formatting.
- Standardized date formats for `order_date` and `ship_date`.
- Created the `shipping_delay_days` column.
- Replaced missing Region values with **Unknown**.
- Replaced missing Ship Mode values with **Unknown**.
- Replaced missing Discount values with **0** only where the required business rule was satisfied.
- Retained remaining missing Discount values as **Unknown** where the business rule was not satisfied.
- Identified duplicate records and duplicate Order IDs.
- Removed exact duplicate records.
- Created calculated columns required for analysis and reporting.
- Generated the Data Quality Report and Pivot Summary Report.

---

## Business Rules Applied

The following business rules were implemented during the cleaning process:

- Missing Region values were replaced with **Unknown**.
- Missing Ship Mode values were replaced with **Unknown**.
- Missing Discount values were replaced with **0** only when **Quantity × Unit Price = Sales**.
- Negative discount values were flagged as **Invalid**.
- Discounts above the allowed range were flagged as **Invalid**.
- Cancelled orders were excluded from completed sales reporting.
- Failed payment records were excluded from completed sales reporting.
- Refunded orders were reported separately.
- Exact duplicated were removed.
- Ship dates earlier than order dates were flagged as **Invalid Shipping Record**.

---

## Summary of Data Quality Issues Found

The following data quality issues were identified during validation:

- Inconsistent text formatting
- Mixed date formats
- Missing values
- Exact duplicate records
- Duplicate Order IDs
- Invalid discount values
- Invalid shipping records
- Cancelled, refunded, and failed payment transactions

These issues were corrected or flagged according to the business rules.

---

## Summary of Final Pivot Reports

The following pivot reports were created:

1. Sales and Profit by Region
2. Sales and Profit by Category and Sub-Category
3. Order Count by Ship Mode
4. Profit Margin by Customer Segment
5. Refunded, Cancelled, and Failed Orders by Region
6. Monthly Sales Trend

Sorting and filtering were applied to the required pivot tables.

---

## Key Business Insights

- Sales performance varied across different regions.
- Product categories contributed differently to total sales and profit.
- Standard Class was the most commonly used shipping method.
- Customer segments showed different average profit margins.
- Cancelled and failed payment records were excluded from completed sales reporting.
- Refunded orders were analysed separately to avoid affecting completed sales analysis.

---

## Assumptions and Limitations

### Assumptions

- A maximum discount value of **1 (100%)** was considered valid.
- Missing Discount values were replaced only when the required business rule was satisfied.
- Conflicting Duplicate Order IDs were retained for business review.
- The original dataset remained unchanged throughout the assignment.

### Limitations

- Conflicting Duplicate Order IDs were retained because additional business verification may be required.
- Some Discount values remained as **Unknown** because the required replacement rule was not satisfied.
- The analysis was performed only on the instructor-provided dataset.

---

## Screenshots Included

The repository contains the following screenshots:

- `screenshots/raw_data_preview.png`
- `screenshots/cleaned_data_preview.png`
- `screenshots/pivot_summary_1.png`
- `screenshots/pivot_summary_2.png`

These screenshots provide evidence of the data cleaning process and the final pivot reports.