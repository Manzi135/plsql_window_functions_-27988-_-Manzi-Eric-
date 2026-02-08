# plsql_window_functions_-27988-_-Manzi-Eric-
# Business Context

A mid-sized e-commerce retail company in the fashion industry, focusing on online sales.
Department: Sales & Marketing Analytics Team

# Data Challenge

The company has noticed that sales vary significantly across regions and months, but it is unclear which products and customer groups are driving these changes. The business also faces low repeat purchases and inefficient marketing campaigns that target all customers the same way. A data-driven analysis is needed to understand product performance, customer purchasing behavior, and customer segments.

 # Expected Outcome

The analysis will identify the top-performing products per region, measure customer purchasing frequency, and create customer segments (e.g., loyal, occasional, high-spenders). These insights will support targeted marketing, improve customer retention, and guide inventory decision
# 1) Top 5 products per region (or per quarter) → RANK()

Measurable Goal:
Identify the top 5 best-selling products in each region (or quarter) based on total revenue (or total units sold) during the selected time period.

Why it matters (Business Decision):
This allows the company to understand which products perform best in different locations so they can:

stock the correct products in each region,

promote products that sell well locally,

reduce overstock of slow-moving items.

What will be measured:

Total sales revenue per product per region

Product ranking within each region (rank 1–5)

Window Function Used:
RANK() to rank products within each region.

# 2) Running monthly sales totals → SUM() OVER()

Measurable Goal:
Calculate the running cumulative monthly sales total for each region to track sales performance over time.

Why it matters (Business Decision):
Running totals help the company monitor:

whether sales are improving steadily,

seasonal sales patterns,

progress toward monthly and quarterly targets.

What will be measured:

Total sales per month per region

Cumulative sales from the first month up to the current month

Window Function Used:
SUM() OVER() to generate cumulative totals across months.

# 3) Month-over-month growth → LAG() / LEAD()

Measurable Goal:
Measure the month-over-month sales growth for each region by calculating:

the difference between current month sales and previous month sales,

the percentage change month-to-month.

Why it matters (Business Decision):
MoM growth helps the business quickly detect:

sudden drops (possible stock-outs, pricing issues, weak marketing),

sudden increases (successful campaigns, seasonal demand),

regions that require improvement actions.

What will be measured:

Current month sales

Previous month sales

MoM sales difference

MoM sales growth percentage

Window Function Used:
LAG() (or LEAD()) to compare sales values between consecutive months.

# 4) Customer quartile segmentation → NTILE(4)

Measurable Goal:
Segment customers into 4 quartiles based on total spending to classify them into groups such as:

top spenders,

medium spenders,

low spenders.

Why it matters (Business Decision):
This segmentation supports targeted marketing such as:

VIP loyalty programs for top spenders,

retention offers for mid-tier customers,

discounts or promotions to increase purchases for low spenders.

What will be measured:

Total spending per customer

Customer quartile group (1–4)

Window Function Used:
NTILE(4) to split customers into 4 equal groups based on spending.

# 5) Three-month moving averages → AVG() OVER()

Measurable Goal:
Compute a 3-month moving average of sales for each region to reduce the effect of short-term fluctuations and identify true trends.

Why it matters (Business Decision):
Monthly sales can fluctuate because of:

promotions,

holidays,

shipping delays,

temporary stock issues.

A moving average helps the company make better decisions for:

inventory planning,

trend analysis,

marketing budgeting.

What will be measured:

Monthly sales per region

3-month rolling average sales per region

Window Function Used:
AVG() OVER() to calculate the rolling 3-month sales average
<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/149d6324-f769-4716-b5da-7cf7382aea1d" />
# REFERENCES
PostgreSQL Global Development Group. (2023). PostgreSQL 16 Documentation: Window Functions.
https://www.postgresql.org/docs/current/functions-window.html

Provides syntax and examples for window functions in SQL.

MySQL. (2023). MySQL 8.0 Reference Manual: Window Functions.
https://dev.mysql.com/doc/refman/8.0/en/window-functions.html

Practical examples of running totals, moving averages, and ranking.

Oracle. (2023). Oracle Database SQL Language Reference: Analytic Functions.
https://docs.oracle.com/en/database/oracle/oracle-database/21/sqlrf/analytic-functions.html
