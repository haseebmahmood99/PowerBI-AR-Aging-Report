# Power BI AR Aging Dashboard

A beginner-friendly Power BI project that analyzes sample invoice data to track accounts receivable performance, overdue balances, and aging buckets.

## Business Goal
Monitor open receivables and collections performance by customer, region, and payment method.

## Tools Used
- Power BI Desktop
- Power Query (data cleaning / transformation)
- DAX (calculated columns and measures)
- CSV sample data
- GitHub (project documentation and versioning)

## Dashboard Features
- KPI cards for total invoiced, total paid, AR open amount, overdue AR amount, and collection rate
- Open AR by customer (bar chart)
- Open AR by aging bucket (column chart)
- Monthly invoiced vs paid trend (line chart)
- Slicers for Status, Region, Payment Method, and Invoice Date
- Invoice-level detail table

## Key Metrics
- Total Invoiced Amount
- Total Paid Amount
- AR Open Amount
- Overdue AR Amount
- Collection Rate %
- Invoice Count

## Sample Screenshot
> Add your screenshot file to the `images/` folder, then update the filename below if needed.

![Dashboard Overview](images/dashboard-overview.png)

## Files in This Repo
- `data/sample_invoices.csv` — mock invoice dataset
- `pbix/AR_Aging_Dashboard.pbix` — Power BI report file
- `images/` — dashboard screenshots
- `README.md` — project overview and documentation

## How to Use
1. Download or clone the repository
2. Open `pbix/AR_Aging_Dashboard.pbix` in Power BI Desktop
3. Explore visuals using slicers
4. (Optional) Replace the CSV with your own sample data and refresh the report

## DAX Examples Used
```DAX
Total Invoiced Amount = SUM(Invoices[InvoiceAmount])

Total Paid Amount = SUM(Invoices[PaidAmount])

AR Open Amount = SUM(Invoices[OpenAmount])

Overdue AR Amount =
CALCULATE(
    [AR Open Amount],
    FILTER(Invoices, Invoices[DaysOverdue] > 0)
)

Collection Rate % = DIVIDE([Total Paid Amount], [Total Invoiced Amount], 0)
```

## Notes
This project was built as a portfolio project to demonstrate beginner Power BI skills in data cleaning, DAX, and dashboard design.

## Possible Next Improvements
- Add more sample rows (100–500+) for a more realistic trend
- Add a Date table for better time intelligence
- Sort aging buckets with a custom sort column
- Add a tooltip page and conditional formatting
