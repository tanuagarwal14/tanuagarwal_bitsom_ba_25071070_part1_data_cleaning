# Cleaning Log

## Overview

This document records the cleaning and validation steps performed on the retail orders dataset. The objective is to prepare a clean and analysis-ready dataset while preserving the original data.

---

## Issues Found

The following issues were identified in the raw dataset:

- Inconsistent text formatting.
- Mixed date formats.
- Missing values in the Region, Ship Mode, and Discount columns.
- Exact duplicate records.
- Duplicate Order IDs.
- Negative discount values.
- Discounts above the allowed range.
- Ship dates earlier than order dates.
- Cancelled, refunded, and failed payment records.

---

## Cleaning Actions Performed

The following cleaning steps are completed:

- Preserved the original dataset in `raw_orders.xlsx`.
- Created a separate cleaned dataset in `cleaned_orders.xlsx`.
- Removed extra spaces and standardized text formatting.
- Standardized the `order_date` and `ship_date` formats.
- Created the `shipping_delay_days` column.
- Replaced missing Region values with **Unknown**.
- Replaced missing Ship Mode values with **Unknown**.
- Replaced missing Discount values with **0** only where the business rule was satisfied.
- Left the remaining missing Discount values as **Unknown** because the business rule was not satisfied.
- Identified exact duplicate records, conflicting duplicate records and duplicate Order IDs.
- Created calculated columns required for reporting and analysis.

---

## Business Rules Applied

The following business rules were applied during data cleaning:

- Missing Region values were replaced with **Unknown**.
- Missing Ship Mode values were replaced with **Unknown**.
- Missing Discount values were replaced with **0** only when **Quantity × Unit Price = Sales**.
- Negative discount values were flagged as **Invalid**.
- Discounts above the allowed range were flagged as **Invalid**.
- Exact duplicates were removed. COnflicting Duplicates were highlighted for review.
- Cancelled orders were excluded from completed sales reporting.
- Failed payment records were excluded from completed sales reporting.
- Refunded orders were reported separately.
- Ship dates earlier than order dates were flagged as **Invalid Shipping Record**.

---

## Assumptions Made

The following assumptions were used during the cleaning process:

- A maximum discount value of **1 (100%)** was considered valid.
- Missing Discount values were replaced only when the specified business rule was satisfied.
- Conflicting Duplicate Order IDs were retained because they may require business review.

---

## Records Removed

Exact Duplicate records were removed during the cleaning process following the business rules. Conflicting Duplicate records were identified and retained for review.

---

## Records Flagged

The following records were flagged during validation:

- Duplicate Order IDs
- Negative discount values
- Discounts above the allowed range
- Invalid shipping records
- Cancelled orders
- Failed payment records
- Refunded orders

---

## Limitations

- Duplicate Order IDs were retained because additional business review may be required.
- Some Discount values remained as **Unknown** because the required business rule for replacing them with **0** was not satisfied.
- The analysis was performed only on the instructor-provided dataset.