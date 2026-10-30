# excel-data-cleaning-project
Turned a messy, real-world spreadsheet of sales records into a polished, analysis-ready dataset. This project focused on fixing everyday data entry errors and handling missing information safely.

# Overview
A beginner data analytics project using an Excel transaction dataset. The workbook includes the original raw data, a conservatively standardized dataset, and a validation summary. Data quality checks were performed to identify missing values, duplicate transaction IDs, inconsistent date formats, and calculation discrepancies. Records requiring further investigation were flagged rather than automatically modified. 

# Dataset
- 50 transaction records and 20 columns in the supplied source workbook.
- Fields include transaction ID/date, customer reference and names, business segment, item, quantity, price, gross amount, region, country, payment method, status, promotion, agent, store, shipping, tax, and feedback score.

# Cleaning actions
- Standardized transaction IDs to a 'TXN' prefix and to use ' _ ' as a separator (e.g. 'ORD_102' -> 'TXN_102').
- Trimmed and standardized customer references (e.g. 'CUST 99' -> 'CUST99').
- Standardized name capitalization.
- Standardized region codes and country values ('NIG and NIGERIA' -> Nigeria).
- Standardized payment-method labels.
- Converted recognizable dates using day-month-year interpretation for dotted and slash-separated dates.
- Converted placeholder text such as null, NaN, Missing, and Unknown to blank values where appropriate.
- Preserved numeric quantities, prices, gross amounts, tax rates, and feedback values; did not guess missing data or automatically remove suspicious records.

# Findings
The workbook's sheets record rule-based checks. Initial checks found:
- 50 raw records and 50 cleaned records (record count preserved).
- 5 missing transaction IDs.
- 2 missing country values.
- 12 missing feedback scores.
- 13 rows participating in duplicate transaction IDs.
- 5 negative quantities in Qty, which result in negative Gross_amt
- Missing transaction ID ending in the digit 6.
- 2 gross-amount mismatches between unit_price and gross_amount
- TXN_107, TXN_108, TXN_111, and TXN_131 each appear twice
- 14 rows flagged by the basic rule-based QA checks.

These findings are **not all confirmed errors**. Duplicate IDs, negative quantities, and amount mismatches require business context and should be investigated before correcting or deleting anything. The source data was retained in 'Raw_Data' for traceability.

# Important assumptions and limitations
- Dotted and dash-separated dates were interpreted as day/month/year where recognizable. Verify this convention with the data owner before analysis.
- The cleaning is conservative: it standardizes clear formatting issues but does not invent missing values or overwrite suspicious numeric values.
- Transaction IDs were normalized to 'TXN' prefix and '_' separator. Review uniqueness before using them as primary keys.
- The missing transaction numbers may be related to a data entry issue, an incomplete transaction sequence, or a problem during data collection.
- Since Prod B consistently appears under Furniture, the missing segment for Prod B may reasonably be inferred as Furniture.

# Skills Demonstrated
Excel data cleaning, text standardization, date parsing, missing-value handling, data validation, duplicate checks, arithmetic consistency checks, documentation, and raw-to-clean comparison.
