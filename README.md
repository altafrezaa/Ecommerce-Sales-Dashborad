ALTAF ECOMMERCE SALES DASHBOARD



📊 Project Overview

ALTAF ECOMMERCE SALES DASHBOARD is an interactive Microsoft Power BI dashboard designed to provide a high-level view of e-commerce sales, profit, quantity, customer performance, payment behavior, geographic/state performance, monthly profit/loss, and product/sub-category profitability.

The dashboard combines KPI cards, bar charts, a column chart, donut charts, slicers, and interactive Power BI filtering into a single-page business intelligence report.

Purpose: Help business users quickly understand how much the business is selling, how profitable it is, what products/categories are driving volume and profit, which states/customers contribute most, how customers pay, and how profit changes month by month.

🎯 Business Objectives

The dashboard is designed to answer questions such as:

What is the total sales amount?

What is the total profit?

How many units/products were sold?

What is the reported AOV metric?

Which states generate the highest sales?

Which product categories contribute most to sales quantity?

Which months are profitable or loss-making?

Which customers contribute the highest sales amount?

Which payment methods are used most frequently?

Which product sub-categories generate the highest profit?

How do the results change when a quarter or state is selected?

🖥️ Dashboard Structure

The report is organized into four main areas:

Header & Filters

KPI Summary Cards

Sales/Profit Analysis

Customer, Payment & Product Analysis

1. Header & Interactive Filters

Dashboard Title

ALTAF ECOMMERCE SALES DASHBOARD

The title identifies the report and establishes the purpose of the page.

Quarter Filter

The top-center buttons contain:

Qtr 1

Qtr 2

Qtr 3

Qtr 4

These act as an interactive quarter-level filter. Selecting a quarter can cross-filter the visuals and KPI cards that are connected to the relevant date/quarter field.

Why it is useful

A business user can compare performance across quarters without creating separate reports for each period.

State Slicer

The top-right States dropdown allows the user to filter the dashboard by state.

The slicer is useful for answering questions such as:

"How does sales performance look for a particular state?"

When a state is selected, connected visuals should update automatically according to the model relationships and visual interactions.

2. KPI Cards

The top row contains four KPI cards.

Total Amount — 438K

Displayed value: 438K

Label: Sum of Amount

This represents the aggregated sales/transaction amount available in the report.

Typical Power BI aggregation:

Total Amount = SUM(Sales[Amount])

Business meaning

This is the overall monetary value of the transactions included in the current filter context.

Total Profit — 37K

Displayed value: 37K

Label: Sum of Profit

This represents the total profit in the current filter context.

Typical DAX:

Total Profit = SUM(Sales[Profit])

Business meaning

It helps determine whether the business is generating positive returns from its transactions.

Total Quantity — 6K

Displayed value: 6K

Label: Sum of Quantity

This represents the total number of units/items sold.

Typical DAX:

Total Quantity = SUM(Sales[Quantity])

Business meaning

Quantity provides a volume-based view of business performance, complementing the monetary sales and profit KPIs.

AOV — 121K

Displayed value: 121K

Label: Sum of AOV

AOV field aggregated using Sum.

AOV commonly means Average Order Value. However, the exact business definition depends on how the source dataset defines the AOV column.

If AOV needs to be calculated from sales data rather than summed from an existing column, a common measure is:

AOV = DIVIDE([Total Amount], DISTINCTCOUNT(Sales[Order ID]))

Important: Do not automatically use the above formula if the original dataset already contains an AOV field. The exact calculation should match the source data/model.

3. Sum of Amount by State

Visual Type

Horizontal Bar Chart

Title

Sum of Amount by State

Purpose

This visual compares sales amount across states.

The dashboard shows approximately:

State

Amount

Maharashtra

102K

Madhya Pradesh

87K

Uttar Pradesh

38K

Delhi

23K

Values are read from the supplied dashboard image and may be rounded because Power BI displays them using abbreviated units.

Power BI configuration

Typical setup:

Y-axis: State

X-axis / Values: Sum of Amount

Data labels: Enabled

Sort: Descending by Amount

Chart: Clustered Bar Chart

Business insight

This chart identifies the strongest geographic contributors to sales. The state with the longest bar contributes the highest sales amount among the displayed states.

4. Sum of Quantity by Category

Visual Type

Donut Chart

Title

Sum of Quantity by Category

The chart divides total sold quantity among product categories.

The Dashboard shows:

Clothing — 63%

Electronics — 21%

Furniture — 17%

Power BI configuration

Legend: Category

Values: Sum of Quantity

Visual: Donut Chart

Detail labels: Category + Percentage

Business insight

The chart shows which major product category contributes the largest share of unit volume.

In the displayed dashboard, Clothing represents the largest share of quantity.

5. Profit-Loss by Month

Visual Type

Column Chart

Title

Profit-Loss by Month

This is one of the most important trend visuals in the dashboard.

It displays monthly profit/loss across the year.

Interpretation

Blue columns: Positive profit

Red columns: Negative profit/loss

Values above zero indicate profitable months.

Values below zero indicate loss-making months.

The month axis contains:

January

February

March

April

May

June

July

August

September

October

November

December

Power BI configuration

X-axis: Month

Y-axis: Sum of Profit

Data labels: Enabled

Conditional colors: Positive vs. negative profit

Sort: Chronological month order

Important Power BI requirement

If the Month field contains text such as January, February, etc., create/use a numeric month-order column so the chart does not sort alphabetically.

Example:

Month Number = MONTH(Sales[Order Date])

Then select:

Month Name → Column tools → Sort by column → Month Number

Business insight

The visual allows management to identify:

Strong profit months

Weak months

Loss-making periods

Seasonal patterns

Potential periods requiring investigation

6. Sum of Amount by Customer Name

Visual Type

Column/Bar Chart

Title

Sum of Amount by CustomerName

This visual compares sales contribution from individual customers.

The dashboard displays four leading customer values at approximately:

9.9K

9.4K

7.6K

6.3K

Power BI configuration

Axis: CustomerName

Values: Sum of Amount

Data labels: Enabled

Sort: Descending by Amount

Business insight

This helps identify high-value customers and supports customer-focused analysis.

Possible business uses:

Customer retention

VIP/customer segmentation

Targeted promotions

Identifying important accounts

Understanding revenue concentration

7. Sum of Quantity by PaymentMode

Visual Type

Donut Chart

Title

Sum of Quantity by PaymentMode

The chart shows how sold quantity is distributed across payment methods.

Visible payment methods include:

COD

UPI

Debit Card

Credit Card

Cash

Approximate percentages shown:

Payment Mode

Share

COD

40%

UPI

21%

Debit Card

13%

Credit Card

12%

Cash

10%

Power BI configuration

Legend: PaymentMode

Values: Sum of Quantity

Visual: Donut Chart

Detail labels: Category + Percentage

Business insight

This visual helps the business understand customer payment preferences and can support decisions around:

Payment gateway priorities

COD operations

Digital payment adoption

Payment-related customer experience

8. Sum of Profit by Sub-Category

Visual Type

Horizontal Bar Chart

Title

Sum of Profit by Sub-Category

The dashborad contains the following sub-categories:

Printers

Bookcases

Sarees

Accessories

Tables

Approximate profit values shown:

Sub-Category

Profit

Printers

6.0K

Bookcases

5.2K

Sarees

4.1K

Accessories

3.0K

Tables

2.8K

Power BI configuration

Axis: Sub-Category

Values: Sum of Profit

Data labels: Enabled

Sort: Descending by Profit

Business insight

This identifies the product groups contributing most strongly to profitability.

A management team can use this visual to investigate:

High-profit products

Low-profit products

Product assortment

Pricing strategies

Inventory priorities

Promotional opportunities

🔄 Dashboard Interactivity

A major advantage of Power BI is that the visuals can interact with each other.

For example:

Selecting a State

Selecting a state from the States slicer can update:

KPI cards

State chart

Category quantity

Monthly profit/loss

Customer sales

Payment-mode distribution

Sub-category profit

Selecting a Quarter

Selecting Qtr 1, Qtr 2, Qtr 3, or Qtr 4 can filter the report to the selected quarter.

Selecting a Chart Element

Clicking a category, state, customer, payment method, or sub-category can cross-highlight/cross-filter other visuals if visual interactions are enabled.

🛠️ Power BI Development Process

The dashboard can be developed using the following workflow.

Step 1 — Collect the Dataset

The source data should contain fields similar to:

Order ID
Order Date
State
Category
Sub-Category
Customer Name
Payment Mode
Amount
Profit
Quantity
AOV

Additional fields may also exist depending on the original dataset.

Step 2 — Import Data into Power BI

Open Power BI Desktop.

Go to:

Home → Get Data

Select the appropriate source, for example:

Excel

CSV

SQL Server

MySQL

Web

Other supported data sources

Load the sales table into Power BI.

Step 3 — Clean Data Using Power Query

Open:

Home → Transform data

Power Query can be used for:

Removing duplicate records

Removing blank rows

Renaming columns

Correcting data types

Handling null values

Cleaning customer/state names

Standardizing category names

Converting date columns

Creating calculated transformation columns

Recommended data types:

Field

Suggested Type

Order ID

Text

Order Date

Date

State

Text

Category

Text

Sub-Category

Text

Customer Name

Text

Payment Mode

Text

Amount

Decimal/Currency

Profit

Decimal/Currency

Quantity

Whole Number

AOV

Decimal/Currency

After transformation:

Home → Close & Apply

Step 4 — Build the Data Model

Open Model view.

If there is only one sales table, the dashboard can be built using that table.

For a more professional production model, use a star schema where appropriate:

                 Date
                  |
                  |
Customer ---- Sales Fact ---- Product
                  |
                  |
              Geography
                  |
              Payment

A typical model could contain:

FactSales

Contains transaction-level information:

Order ID

Order Date

Customer ID

Product ID

State ID

Payment Mode ID

Quantity

Amount

Profit

Dimension tables

Examples:

DimDate

DimCustomer

DimProduct

DimGeography

DimPayment

This structure can improve scalability, filtering, and maintainability.

Step 5 — Create Measures

Recommended core measures:

Total Amount =
SUM(Sales[Amount])

Total Profit =
SUM(Sales[Profit])

Total Quantity =
SUM(Sales[Quantity])

Total Orders =
DISTINCTCOUNT(Sales[Order ID])

Profit Margin % =
DIVIDE([Total Profit], [Total Amount], 0)

If AOV is calculated from orders:

AOV =
DIVIDE([Total Amount], [Total Orders], 0)

Why measures are preferred

Measures respond dynamically to filters and slicers. For example, when a user selects a state or quarter, the measure recalculates for the selected filter context.

Step 6 — Create a Date Table

For reliable time intelligence, create a dedicated Date table.

Example:

DateTable =
ADDCOLUMNS(
    CALENDAR(
        MIN(Sales[Order Date]),
        MAX(Sales[Order Date])
    ),
    "Year", YEAR([Date]),
    "Month Number", MONTH([Date]),
    "Month", FORMAT([Date], "MMM"),
    "Quarter", "Qtr " & FORMAT([Date], "Q")
)

Then create a relationship:

DateTable[Date] → Sales[Order Date]

Mark the table as a Date table in Power BI when appropriate.

Step 7 — Create the Visuals

KPI Cards

Create four Card visuals:

Total Amount
Total Profit
Total Quantity
AOV

State Chart

Use:

Clustered Bar Chart

Y-axis  → State
X-axis  → Total Amount

Enable:

Data labels

Sorting

Appropriate display units

Category Donut

Use:

Donut Chart

Legend → Category
Values → Total Quantity

Monthly Profit/Loss

Use:

Clustered Column Chart

X-axis → Month
Y-axis → Total Profit

Use conditional formatting or a profit/loss color rule so positive and negative values are visually distinct.

Customer Chart

Use:

Clustered Column Chart

X-axis → Customer Name
Y-axis → Total Amount

Sort customers by amount.

If the goal is specifically to show only the highest customers, use a Top N filter.

Payment Mode Donut

Use:

Donut Chart

Legend → Payment Mode
Values → Total Quantity

Sub-Category Profit

Use:

Clustered Bar Chart

Y-axis → Sub-Category
X-axis → Total Profit

Sort descending by profit.

🎨 Dashboard UI/UX Design

The dashboard uses a dark, modern, technology-style theme.

Main design characteristics

Dark purple/navy background

Magenta/purple visual borders

Bright blue data bars

Red negative-profit bars

Green, yellow, orange, and purple category/payment segments

White/light text

Rounded visual containers

Large KPI numbers

Compact dashboard layout

Why this design works

The dark background creates strong contrast with the charts and KPI values, while the bright chart colors make important business information easy to distinguish.

📐 Suggested Page Layout

The current layout follows a logical dashboard hierarchy:

┌──────────────────────────────────────────────────────────────┐
│ Dashboard Title        Quarter Filters       State Slicer    │
├──────────┬──────────┬──────────┬──────────┬─────────────────┤
│ Amount   │ Profit   │ Quantity │ AOV      │ Profit/Loss     │
├──────────┴──────────┴──────────┴──────────┤                 │
│ Amount by State │ Quantity by Category     │ Monthly Trend   │
├─────────────────┼─────────────────────────┼─────────────────┤
│ Customer Amount │ Payment Mode Quantity    │ Profit by       │
│                 │                         │ Sub-Category    │
└─────────────────┴─────────────────────────┴─────────────────┘

This arrangement follows a useful BI principle:

KPIs → Trends → Breakdown → Detailed Analysis

📌 What the Dashboard Shows

The dashboard currently communicates the following high-level results:

Overall performance

Total Amount: 438K

Total Profit: 37K

Total Quantity: 6K

Reported AOV metric: 121K

Geographic performance

The state chart shows Maharashtra as the largest displayed contributor, followed by Madhya Pradesh, Uttar Pradesh, and Delhi.

Category performance

Clothing accounts for the largest displayed share of quantity at approximately 63%, followed by Electronics and Furniture.

Monthly profitability

The monthly chart contains both profitable and loss-making months, allowing the user to identify periods of strong and weak financial performance.

Customer performance

The customer chart highlights the highest-value customers by total transaction amount.

Payment behavior

COD is the largest displayed payment-mode share at approximately 40%, followed by UPI, Debit Card, Credit Card, and Cash.

Product profitability

Printers is the highest-profit displayed sub-category, followed by Bookcases, Sarees, Accessories, and Tables.


👨‍💻 Author

Altaf Reza

Project: ALTAF ECOMMERCE SALES DASHBOARD
Platform: Microsoft Power BI
Project Type: Business Intelligence / Data Analytics / Sales Dashboard

⭐ Project Summary

This Power BI project converts raw e-commerce transaction data into an interactive management dashboard. Instead of reviewing individual transactions manually, users can monitor overall sales and profit KPIs, investigate geographic performance, understand product/category demand, identify valuable customers, analyze payment preferences, and track monthly profitability from a single report page.

The dashboard is intended to support data-driven decision making by presenting important business metrics in a clear, interactive, and visually accessible format.
