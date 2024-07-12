# Amazon Sales Analysis

![Amazon Sales Analysis](https://github.com/ArunJakhmola/arunjakhmola.github.io/blob/main/assets/Screenshot%202024-07-12%20134827.png)

## Project Overview

This project aims to analyze sales data from Amazon to uncover insights and trends. The analysis includes data cleaning, visualization, and extracting key metrics to provide a comprehensive overview of the sales performance.

## Introduction

The Amazon Sales Analysis project involves analyzing sales data to identify trends and patterns that can help in making informed business decisions. The project covers various aspects of data analysis including data preprocessing, exploratory data analysis, and visualization.

## Dataset

The dataset used in this project is sourced from Amazon's sales records. It includes details such as product ID, product name, sales amount, date of sale, and more.

## Libraries Used

The following Python libraries are used in this project:

- **Pandas**: For data manipulation and analysis
- **Matplotlib**: For creating static, animated, and interactive visualizations
- **Seaborn**: For statistical data visualization
- **Jupyter Notebook**: For organizing and sharing the analysis

## Project Structure

The project files are structured as follows:

- `Amazon Sales Analysis.ipynb`: Jupyter Notebook containing the analysis code
- `README.md`: Project overview and documentation (this file)

## Analysis Questions and Code

### 1. What are the top-selling products?

```python
# Load data
import pandas as pd
data = pd.read_csv('amazon_sales_data.csv')

# Top-selling products
top_selling_products = data.groupby('product_name').sum()['sales_amount'].sort_values(ascending=False).head(10)
print(top_selling_products)
```

### 2. What are the monthly and yearly sales trends?
```python

# Convert date column to datetime
data['date'] = pd.to_datetime(data['date'])

# Monthly sales trend
monthly_sales = data.resample('M', on='date').sum()['sales_amount']
print(monthly_sales)

# Yearly sales trend
yearly_sales = data.resample('Y', on='date').sum()['sales_amount']
print(yearly_sales)
```

### 3. What is the correlation between different variables?
```python

# Correlation matrix
correlation_matrix = data.corr()
print(correlation_matrix)
```

### 4. Which categories contribute the most to sales?
```python

# Sales by category
category_sales = data.groupby('category').sum()['sales_amount'].sort_values(ascending=False)
print(category_sales)
```

### 5. Are there any seasonal trends in the sales data?
```python

# Monthly sales trend to observe seasonality
monthly_sales.plot()
```

### 6. How does the sales performance vary across different regions?
````python

# Sales by region
region_sales = data.groupby('region').sum()['sales_amount']
print(region_sales)
````

### Results
The key findings from the analysis include:

- Identification of top-selling products
- Monthly and yearly sales trends
- Correlation between different variables

### Conclusion
The analysis provided valuable insights into Amazon's sales performance. These insights can help in optimizing inventory management, marketing strategies, and overall business operations.

### Future Work
Potential future improvements and extensions of this project include:

- Incorporating additional data sources for a more comprehensive analysis
- Implementing machine learning models to predict future sales
- Developing interactive dashboards for real-time sales monitoring

