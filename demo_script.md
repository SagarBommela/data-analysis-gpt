# BizMetrics Assistant — Loom Demo Script


This is my Topic 13 Custom GPT Hands-On assessment.

The project is called BizMetrics Assistant.

The objective is to demonstrate a responsible data-analysis assistant that can work with uploaded CSV data, identify data-quality problems, ask clarification questions when necessary, and avoid fabricating numerical insights.

The project contains four main artifacts:

- instruction_block.md
- sample_sales_data.csv
- test_results.md
- README.md

---

## Part 1 — Project Structure

Show the project folder.



README.md
- Project overview and implementation documentation.

instruction_block.md
- Contains the BizMetrics Assistant instructions, data-quality rules, tool governance, and anti-fabrication guardrails.

sample_sales_data.csv
- Contains sales transactions with deliberately introduced data-quality issues.

test_results.md
- Contains the four required test scenarios and their actual results.

---

## Part 2 — Instruction Block

Open instruction_block.md.

Show the following sections:

1. Role
2. Persona and Communication Style
3. Analysis Objective
4. Data Quality Check
5. Code Interpreter / Data Analysis Tool Governance
6. Anti-Fabrication Guardrails
7. Missing Data Handling
8. Duplicate Handling
9. Ambiguous Business Questions
10. Final Accuracy Rule

"The important design principle is that the assistant should not guess. It should verify the user's objective, inspect data quality, use calculations for numerical findings, and clearly communicate limitations."

---

## Part 3 — Sample Dataset

Open sample_sales_data.csv.



- Date
- Product
- Region
- Customer
- Quantity
- Sales Amount

Then show the deliberate issues:

- Blank Sales Amount
- N/A Sales Amount
- Duplicate transaction



"I intentionally included these issues so that the assistant can be tested against realistic data-quality problems."

---

## Part 4 — Scenario 1: Clear Objective

Upload sample_sales_data.csv.



"What were my total sales by month?"


"This is a clear analytical objective, so the assistant should perform the requested analysis while checking the relevant data quality."


---

## Part 5 — Scenario 2: No Objective


"Here's my data."



"The user has provided data but has not provided an analytical objective. The assistant should not perform unsolicited analysis."


---

## Part 6 — Scenario 3: Data Quality Problem



"What are my total sales?"



"This scenario tests whether the assistant detects the blank value, N/A values, and duplicate transaction before producing a potentially misleading result."




---

## Part 7 — Scenario 4: Ambiguous Goal



"Is my business doing well?"



"This is too broad to answer responsibly. The assistant should request a measurable business-performance objective rather than making an unsupported business-health conclusion."



---

## Part 8 — Test Results



"I recorded the actual assistant outputs, expected behavior, pass/fail result, and observations in the test-results document."

---

## Part 9 — Assessment Summary


"The implementation demonstrates objective confirmation, data-quality validation, tool governance, anti-fabrication controls, and plain-language reporting."



This completes my Topic 13 assessment for the BizMetrics Assistant data-analysis workflow.