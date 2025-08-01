# 🧾 Sales Analysis with Pandas

This project performs data analysis on a sample food sales dataset using **Python** and **Pandas**. It showcases basic data manipulation, filtering by region, updating prices, and calculating total revenue, along with trend analysis and visualizations.

## 📂 Dataset

- File: `sampledatafoodsales.xlsx`
- Columns:
  - `OrderDate`: Date of order
  - `Region`: Sales region (East or West)
  - `City`: City of sale
  - `Category`: Product category
  - `Product`: Name of the product
  - `Quantity`: Units sold
  - `UnitPrice`: Price per unit
  - `TotalPrice`: Total revenue (`Quantity * UnitPrice`)

## 📊 Features

- Load and display the dataset using **Pandas**
- Filter data by region (East, West)
- Apply a 15% price increase to `UnitPrice`
- Recalculate `TotalPrice` accordingly
- Extract and analyze sales data for specific cities (e.g. `New York`)
- Visualize trends in product sales over time
- Generate plots to compare regions and products

---

## 📈 Trend Analysis

The project includes simple trend analysis based on `OrderDate` and `TotalPrice`. This helps in identifying:
- Monthly or yearly sales performance
- Top-performing cities or products
- Regional sales comparison over time

### Sample Code

```python
# Convert 'OrderDate' to datetime
sales['OrderDate'] = pd.to_datetime(sales['OrderDate'])

# Group by month and sum total sales
monthly_sales = sales.resample('M', on='OrderDate')['TotalPrice'].sum()

# Plot trend
import matplotlib.pyplot as plt

plt.figure(figsize=(12,6))
monthly_sales.plot(kind='line', marker='o')
plt.title('Monthly Total Sales Trend')
plt.xlabel('Month')
plt.ylabel('Total Sales ($)')
plt.grid(True)
plt.tight_layout()
plt.show();
```

## Optional Extensions
You can also perform:

Year-over-year or quarter-over-quarter analysis

Category-wise trends using groupby(['Category', 'OrderDate'])

Region-wise trends using groupby(['Region', 'OrderDate'])

🧪 Tech Stack
Python 3

Pandas

NumPy

Matplotlib

Jupyter Notebook

📌 How to Run
Clone this repository:

```
git clone https://github.com/your-username/sales-analysis.git
cd sales-analysis
```
Open the notebook:

```
jupyter notebook Sales analysis.ipynb
Update the file path:
sales = pd.read_excel('your_path_to/sampledatafoodsales.xlsx')
```
#📎 Sample Code Snippets
```
# Filter East region sales
east_sales = sales[sales['Region'] == 'East']

# Apply 15% price increase
sales['UnitPrice'] *= 1.15

# Recalculate TotalPrice
sales['TotalPrice'] = sales['Quantity'] * sales['UnitPrice']
```

📌 Author:

Patrick Anieke Chibuzor
(Solutions Architect)

📜 License
This project is licensed under the MIT License.
