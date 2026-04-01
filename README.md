# Superstore Sales Analysis

This project analyzes a retail Superstore sales dataset using Python and Power BI. It covers data cleaning, feature engineering, exploratory analysis, dashboarding, and a simple machine learning model to predict shipping duration.

## Project Overview

The workflow in this project includes:

- Loading Superstore sales data into a Jupyter notebook
- Cleaning date and postal code fields
- Creating time-based features such as year, month, weekday, quarter, and shipping days
- Performing exploratory data analysis with `pandas`, `matplotlib`, and `seaborn`
- Exporting a transformed dataset for reporting
- Building a Power BI dashboard
- Training a `RandomForestRegressor` to predict `Shipping Days`

## Files

- `sales_data_analysis.ipynb` - main notebook for analysis, feature engineering, export, and modeling
- `superstore_sales.csv` - transformed dataset with engineered columns
- `sales.csv` - raw source dataset used for analysis
- `superstore_sales_Dashboard.pbix` - Power BI dashboard file
- `dashboard.png` - dashboard preview image

## Dataset

The dataset contains 9,800 rows and 18 original columns, including:

- order and shipping dates
- customer, segment, and region fields
- product category and sub-category
- product name
- sales amount

The notebook engineers these additional columns:

- `Year`
- `Month`
- `Order Day`
- `Order Weekday`
- `Month Name`
- `Quarter`
- `Shipping Days`

## Analysis Highlights

From the notebook output:

- Highest total sales region: `West` with `710,219.6845`
- Highest average sales category: `Technology` with `456.401474`
- Top product by total sales: `Canon imageCLASS 2200 Advanced Copier` with `61,599.824`

The notebook also includes:

- a correlation heatmap for numeric features
- a bar chart of total sales by category
- grouped summaries for region and category performance

## Machine Learning

The notebook builds a regression model to predict `Shipping Days`.

- Model: `RandomForestRegressor`
- Train/test split: `80/20`
- Reported result: `Random Forest MAE = 0.7546490025484379`

Before modeling, the notebook:

- drops identifier and free-text columns such as `Row ID`, `Order ID`, `Customer Name`, `Product Name`, `Order Date`, and `Ship Date`
- one-hot encodes categorical variables with `pd.get_dummies(..., drop_first=True)`

## Tools and Libraries

- Python 3
- Jupyter Notebook
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- Power BI Desktop

## How to Run

1. Open `sales_data_analysis.ipynb` in Jupyter Notebook or VS Code.
2. Make sure the input CSV path matches a file in this folder.
3. Install required Python packages if needed:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn notebook
```

4. Run the notebook cells in order.
5. Open `superstore_sales_Dashboard.pbix` in Power BI Desktop to view or edit the dashboard.

## Important Notes

The notebook currently loads:

```python
df = pd.read_csv("train.csv")
```

The notebook also exports:

```python
df.to_csv("superstore_sales.csv"", index=False)
```

But the repository currently contains `superstore_sales.csv` instead of `Sales.csv`. Standardizing these names would make the project easier to reproduce.

## Outputs

- cleaned and feature-enriched sales data exported to CSV
- Python-based charts for exploratory analysis
- Power BI dashboard for business reporting
- shipping time prediction model

## Suggested Improvements

- add a `requirements.txt`
- standardize file names so notebook inputs and outputs match the repository
- add dashboard screenshots and KPI descriptions
- save the trained model or feature importances
- include a short business insights section based on the analysis
