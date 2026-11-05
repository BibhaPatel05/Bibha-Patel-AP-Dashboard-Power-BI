# Bibha-Patel-AP-Dashboard-Power-BI

A 4-page interactive Power BI dashboard that tracks invoices, payments, vendor risk and aging for a sample company.

## Key findings
- 6.33M invoiced across 998 invoices: 4.70M paid (74%) and 1.63M outstanding
- 98% of outstanding AP is overdue
- About 82% of outstanding AP (1.33M) is more than 120 days old
- Insight Partners, LegalEdge LLP and SecureNet hold the largest outstanding balances
- Insight Partners has the lowest payment rate (57%)

## Dashboard pages
| Page | What it shows |
|---|---|
| Overview | Total invoiced, paid, outstanding, monthly trend, top vendors, status split |
| Vendor Analysis | Vendor-level paid, outstanding, overdue and payment rate |
| AP Aging | Outstanding amount by aging bucket and overdue counts |
| Payment Analysis | Payments by method, month and vendor |


## Data model
Star schema: `Fact_Invoice` and `Fact_Payment` (facts), `Dim_Vendor` and `Dim_Date` (dimensions).

## Key DAX measures
- Total Invoice Amount, Total Paid, Outstanding Amount
- Overdue Amount, Overdue Invoice Count, Overdue % of Outstanding
- Payment Rate, Average Payment Value
- Aging Bucket (calculated column, as-of date 31 Aug 2026)

## Assumptions and limitations
- Aging uses a fixed as-of date of 31 Aug 2026 so results are reproducible (use TODAY() for live data)
- Invoices dated after the as-of date (2027) are excluded
- Amounts are summed as stored, with no currency conversion
- One invoice has no due date and is shown in its own "No Due Date" bucket
- The payment trend groups by invoice month, not payment date

## Tools
Power BI Desktop, DAX, Power Query

## Files
- `AP_Dashboard.pbix`: the Power BI file (open in Power BI Desktop)
- `Bibha_Patel_AP_Dashboard_Power_BI.pdf`: PDF export of all pages
- `data/`: sample source data

## Author
Bibha Patel | [www.linkedin.com/in/bibha-p-7603641b8)

<img width="720" height="400" alt="image" src="https://github.com/user-attachments/assets/8e30d8d9-dbc2-4653-8f7d-c01abf5fb56b" />

