# Superstore Sales Analysis

This project analyzes a retail superstore dataset with Python and presents the results in Power BI. The repository includes the raw sales data, a Jupyter notebook for cleaning and analysis, an exported feature-enriched dataset, and a Power BI dashboard file.

## Project Contents

- `Sales.csv`: raw input dataset with 9,800 rows and 18 columns
- `sales_data_analysis.ipynb`: notebook for data cleaning, feature engineering, EDA, export, and modeling
- `superstore_sales.csv`: transformed dataset exported by the notebook
- `superstore_sales_Dashboard.pbix`: Power BI dashboard project
- `dasnboard.png`: dashboard preview image

## Workflow

The notebook performs the following steps:

1. Loads `Sales.csv`
2. Converts `Order Date` and `Ship Date` to datetime
3. Fills missing `Postal Code` values and casts them to integers
4. Creates additional time-based features:
   - `Year`
   - `Month`
   - `Order Day`
   - `Order Weekday`
   - `Month Name`
   - `Quarter`
   - `Shipping Days`
5. Generates exploratory analysis outputs, including:
   - correlation heatmap for numeric columns
   - sales by category chart
   - grouped summaries by region, category, and product
6. Exports the transformed data to `superstore_sales.csv`
7. Trains a `RandomForestRegressor` to predict `Shipping Days`

## Dataset Summary

The raw dataset contains these core fields:

- order and shipping identifiers
- ship mode
- customer and segment information
- geographic fields such as city, state, postal code, and region
- product category and sub-category
- product name
- sales value

The exported dataset expands the original 18 columns to 25 columns through feature engineering.

## Notebook Results

Saved notebook outputs show:

- Highest total sales region: `West` (`710,219.6845`)
- Highest average sales category: `Technology` (`456.401474`)
- Top product by total sales: `Canon imageCLASS 2200 Advanced Copier` (`61,599.824`)
- Random forest mean absolute error for shipping-day prediction: `0.7546490025484379`

Regional sales totals from the notebook:

- `West`: `710,219.6845`
- `East`: `669,518.7260`
- `Central`: `492,646.9132`
- `South`: `389,151.4590`

## Power BI Dashboard

The repository also includes a Power BI report file, `superstore_sales_Dashboard.pbix`, plus a preview image in `dasnboard.png`. The dashboard complements the notebook analysis with an interactive reporting layer.

## How to Run

1. Open `sales_data_analysis.ipynb` in Jupyter Notebook or VS Code.
2. Install the required packages if they are not already available:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn notebook
```

3. Run the notebook cells in order.
4. Open `superstore_sales_Dashboard.pbix` in Power BI Desktop to inspect or edit the dashboard.

## Current Repository Notes

- The notebook reads from `Sales.csv` and writes to `superstore_sales.csv`. Those filenames are consistent with the files currently stored in the repository.
- The dashboard preview image is named `dasnboard.png`. If you want stricter naming consistency, rename it to `dashboard.png` and update references accordingly.
- There is no `requirements.txt` or environment file yet, so Python dependencies are documented here instead of being pinned in the repo.

## Suggested Next Improvements

- add a `requirements.txt`
- document dashboard KPIs and filters
- include a short business-insights section derived from the analysis
- save model feature importance or persist the trained model artifact
