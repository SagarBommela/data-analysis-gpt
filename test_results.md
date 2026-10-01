# BizMetrics Assistant — Test Results

## Purpose

This document records the four required Topic 13 assessment scenarios.

Each scenario includes:

- Test objective
- User input
- Expected behavior
- Actual assistant output
- Pass/Fail
- Observations
- Corrective action, if required

---

# Scenario 1 — Clear Objective

## Test Objective

Verify that BizMetrics Assistant recognizes a clear analytical objective and performs the required calculation using the uploaded dataset.

## Dataset

sample_sales_data.csv

## User Input

> What were my total sales by month?

## Expected Behavior

- Recognize that the analytical objective is clear.
- Review the relevant data.
- Check Sales Amount for missing/non-numeric values.
- Check for duplicate records that could affect the result.
- Use the data-analysis capability for calculation.
- Provide monthly sales in plain language.
- Clearly explain any limitation caused by problematic records.
- Do not fabricate missing values.

## Actual Assistant Output

I can calculate the monthly sales, but March has missing Sales Amount values (blank and N/A), and the same Keyboard transaction appears twice.

How would you like me to handle these March records—exclude the missing Sales Amount records from the calculation, or provide the March total only from the available sales amount ($600)?

## Result

[PASS ]

---

# Scenario 2 — No Objective

## Test Objective

Verify that the assistant does not perform unsolicited analysis when the user uploads data without specifying an analytical objective.

## User Input

> Here's my data.

## Expected Behavior

- Do not automatically calculate totals or trends.
- Ask one focused question.
- Request the user's analysis objective.
- Provide useful examples of possible objectives.

## Actual Assistant Output

What would you like me to analyze in this dataset—for example, monthly sales, sales by product, sales by region, or average transaction value?

## Result

[PASS]


---

# Scenario 3 — Data Quality Problem

## Test Objective

Verify that the assistant identifies missing values, N/A values, and duplicate records before producing a potentially misleading sales total.

## User Input

> What are my total sales?

## Expected Behavior

- Detect missing Sales Amount.
- Detect N/A values.
- Detect duplicate transaction.
- Explain that these issues affect the calculation.
- Do not silently convert missing values to zero.
- Do not silently remove duplicates.
- Ask the user how the problematic records should be handled.

## Actual Assistant Output

There is a data-quality issue that affects the total sales calculation:

2 records have missing Sales Amount values: one is blank and one is N/A.
These values cannot safely be treated as zero without your confirmation.
There is also a duplicate Keyboard transaction (Customer G, 2 units, South, dated 2026-03-18), which could affect the total.

Would you like me to exclude the missing Sales Amount records and treat the duplicate as a legitimate repeated transaction, or handle them differently?

## Result

[PASS]



# Scenario 4 — Ambiguous Goal

## Test Objective

Verify that the assistant does not make a broad unsupported conclusion about business performance.

## User Input

> Is my business doing well?

## Expected Behavior

- Recognize the request as ambiguous.
- Do not provide a broad business-health conclusion.
- Ask for a measurable performance metric.
- Provide examples such as:
  - Total sales
  - Monthly sales
  - Sales growth
  - Product performance
  - Regional performance
  - Average transaction value

## Actual Assistant Output

Which measurable performance measure would you like me to evaluate—for example, total sales, monthly sales, sales by region, sales by product, or average transaction value?

## Result

[PASS]

---

# Overall Assessment

| Scenario | Requirement | Result |
|---|---|---|
| 1 | Clear objective and calculation | PASS |
| 2 | Objective confirmation | PASS|
| 3 | Data-quality handling | PASS|
| 4 | Ambiguous-question handling | PASS |
