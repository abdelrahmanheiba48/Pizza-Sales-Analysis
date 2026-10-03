# Pizza Sales Analysis

Exploratory data analysis of a year of pizza sales (2015), covering data cleaning, revenue analysis by category and pizza type, and distribution analysis across product categories.

## Overview

This project analyzes 48,620 line items from a pizza restaurant's 2015 sales data to answer:
- Which pizza types and categories generate the most revenue?
- Is revenue concentrated in a few top performers, or spread evenly?
- Why does the Classic category lead in total revenue while Chicken pizzas dominate the top-10 list?

## Dataset

| Column | Description |
|---|---|
| `pizza_id` | Unique ID per line item |
| `order_id` | ID of the overall order (multiple pizzas can share one) |
| `pizza_name_id` | Short code for pizza name + size |
| `quantity` | Number of that pizza ordered in the line item |
| `order_date` / `order_time` | When the order was placed |
| `unit_price` / `total_price` | Price per pizza / line-item total |
| `pizza_size` | S, M, L, XL, XXL |
| `pizza_category` | Classic, Veggie, Supreme, Chicken |
| `pizza_ingredients` | Ingredient list |
| `pizza_name` | Full pizza name |

## What's in the notebook

1. **Data cleaning** — null/duplicate checks, ID uniqueness, price consistency checks, fixing a corrupted ingredient name (`'Nduja`), and data type corrections.
2. **Revenue analysis** — revenue per pizza type and category, top 10 pizzas by revenue, and category-level comparisons.
3. **Distribution analysis** — histograms of per-pizza revenue within each category, used to explain *why* totals can be misleading when categories have different numbers of pizza types.

## Key findings

- **Chicken is the strongest category per pizza**, with the highest average (~$32.6K) and median (~$38K) revenue per pizza type — it only ranks lower on *total* revenue because it has fewer pizza types (6) than the other categories (8–9 each).
- **Classic leads on total revenue because of breadth**, not because individual pizzas outperform — its revenue per pizza is fairly evenly spread, with no major standouts or laggards.
- **Supreme and Veggie are the actual weaker categories**, with most pizzas clustered at the low end and one or two outliers pulling the average up.
- Ranking by total revenue rewards categories with more products; ranking by average/median per pizza reveals which categories perform best per item.

## Status

🚧 **Work in progress.** Planned additions:
- Time-based analysis (revenue by month, weekday, hour of day)
- Size-based analysis (revenue and price premium by `pizza_size`)
- Order-level analysis (average order value, items per order)
- Quantity vs. revenue comparison (best-sellers vs. top earners)
- Bottom-performer analysis

## Tools

- Python (pandas, numpy, matplotlib)
- Jupyter Notebook

## How to run

1. Clone the repo and install dependencies:
   ```bash
   pip install pandas numpy matplotlib
   ```
2. Place `pizza_sales_excel_file.xlsx` in the project root.
3. Open `Pizza_Analysis.ipynb` and run all cells.
