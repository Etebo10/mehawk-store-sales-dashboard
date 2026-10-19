# Data Dictionary

File: `data/mehawk_store_orders.csv` (also the **Database** sheet in the workbook)
Size: 9,994 rows x 20 columns. Each row is one order line.

| Column | Type | Description |
|---|---|---|
| Row ID | Integer | Unique row number (1 to 9,994) |
| Order Date | Date | Date the order was placed (2011-01-04 to 2014-12-31) |
| Year | Integer | Year of the order date |
| Month | Text | Month of the order date, abbreviated (Jan to Dec) |
| Ship Date | Date | Date the order was shipped |
| Delivery Time | Integer | Days between Order Date and Ship Date |
| Ship Mode | Text | First Class, Same Day, Second Class, Standard Class |
| Customer Name | Text | Customer (793 unique) |
| Segment | Text | Consumer, Corporate, Home Office |
| Country | Text | United States, blank on 4,093 rows |
| City | Text | City (531 unique) |
| State | Text | US state (49 unique) |
| Region | Text | Central, East, South, West |
| Category | Text | Furniture, Office Supplies, Technology |
| Sub-Category | Text | 17 sub-categories (Phones, Chairs, Binders, and so on) |
| Product Name | Text | Product (1,841 unique) |
| Sales | Decimal | Revenue of the order line, in $ |
| Quantity | Integer | Units sold on the order line |
| Discount | Decimal | Discount applied, from 0 to 0.8 (0% to 80%) |
| Profit | Decimal | Profit of the order line, in $. Negative means a loss |

## Calculated measures used in the dashboard

| Measure | Definition |
|---|---|
| Profit Margin | Total Profit / Total Sales |
| Units Sold | Sum of Quantity |
| Order Lines | Number of rows (the dataset has no Order ID) |
| Top (segment, category, region, sub-category) | Highest Sales within the active filters |
| Pareto class | A = first 80% of cumulative sales, B = next 15%, C = last 5% |

## Cleaning applied

| Issue found | Action |
|---|---|
| `Year` stored as text | Converted to a number |
| `Delivery Time` used a function that needs Excel 2013+ | Replaced with Ship Date minus Order Date |
| `Country` blank on 41% of rows | Left as is, not used |
| Possible duplicate (Row IDs 3406 and 3407) | Kept and flagged |
| "Staples" appears under 10 sub-categories | Treated as one combined product in product rankings |
