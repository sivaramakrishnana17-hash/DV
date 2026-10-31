
� Superstore Sales Data Analysis Using Python
📌 Project Overview
This project performs Exploratory Data Analysis (EDA) on the Superstore dataset using Python. The main
goal is to understand sales patterns, analyze product categories, examine sales distribution, and calculate
the number of days taken to ship orders.
The project uses popular Python data science and visualization libraries such as Pandas, NumPy,
Matplotlib, and Seaborn.
🎯 Objectives
The main objectives of this project are:
• 
• 
• 
• 
• 
• 
• 
• 
• 
To load and explore the Superstore dataset.
To understand the structure and summary statistics of the data.
To convert date columns into the proper datetime format.
To calculate the delivery time for each order.
To identify unique product categories.
To check for missing values in the dataset.
To analyze total sales for each category.
To visualize sales by category.
To understand the distribution of sales values.
🛠️ Technologies and Libraries Used
• 
• 
• 
• 
• 
• 
Python
Pandas – Data manipulation and analysis
NumPy – Numerical operations
Matplotlib – Data visualization
Seaborn – Statistical data visualization
Google Colab / Jupyter Notebook – Development environment
📂 Dataset
The project uses the Superstore Dataset, which contains information related to orders and sales.
The dataset is loaded using:
1
df = pd.read_csv("/content/samplesuperstore.csv")
Important Columns Used
• 
• 
• 
• 
Order Date – Date on which the order was placed.
Ship Date – Date on which the order was shipped.
Category – Product category.
Sales – Sales amount.
🔍 Data Analysis Process
1. Importing Libraries
The required Python libraries are imported for data analysis and visualization.
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
2. Loading the Dataset
The Superstore CSV dataset is loaded into a Pandas DataFrame.
df = pd.read_csv("/content/samplesuperstore.csv")
3. Exploring the Dataset
The first few rows of the dataset are displayed using:
df.head()
The structure and data types of the dataset are examined using:
df.info()
Summary statistics are obtained using:
2
df.describe()
4. Date Conversion
The 
Order Date and 
Ship Date columns are converted into datetime format.
df['Order Date'] = pd.to_datetime(df['Order Date'])
df['Ship Date'] = pd.to_datetime(df['Ship Date'])
This allows date-based calculations and analysis.
5. Calculating Delivery Days
A new column named 
Delivery Days is created to calculate the number of days between order
placement and shipping.
df['Delivery Days'] = (df['Ship Date']- df['Order Date']).dt.days
This helps analyze the shipping time of orders.
6. Finding Unique Categories
The unique product categories available in the dataset are identified using:
df['Category'].unique()
7. Checking Missing Values
Missing values in each column are checked using:
df.isnull().sum()
This step helps determine whether data cleaning is required.
8. Category-wise Sales Analysis
The total sales for each product category are calculated using the 
groupby() function.
category_sales = df.groupby('Category')['Sales'].sum()
3
This provides a comparison of sales performance across different product categories.
📊 Data Visualization
Sales by Category
A bar chart is created to visualize the total sales for each category.
category_sales.plot(kind='bar', figsize=(8,5))
plt.title("Sales by Category")
plt.ylabel("Total Sales")
plt.show()
This visualization makes it easier to compare the sales performance of different product categories.
Sales Distribution
A histogram is created using Seaborn to understand the distribution of sales values.
plt.figure(figsize=(8,5))
sns.histplot(df['Sales'], bins=30)
plt.title("Sales Distribution")
plt.show()
The histogram helps identify how frequently different sales values occur in the dataset.
📈 Key Analysis Performed
The project performs the following analysis:
Analysis
Dataset Exploration
Descriptive Statistics
Date Conversion
Delivery Days Calculation
Category Identification
Missing Value Analysis
Purpose
Understand the dataset structure
Analyze numerical data
Prepare dates for analysis
Measure shipping time
Find available product categories
Check data quality
4
Analysis
Purpose
Category-wise Sales
Compare sales performance
Sales Distribution
Understand sales patterns
💡 Insights
The analysis helps in understanding:
• 
• 
• 
• 
• 
• 
Which product categories generate higher total sales.
How sales values are distributed.
The shipping duration of customer orders.
The overall structure and quality of the dataset.
Whether the dataset contains missing values.
Different patterns and trends in Superstore sales data.
🚀 How to Run the Project
Step 1: Install Required Libraries
pip install pandas numpy matplotlib seaborn
Step 2: Download the Dataset
Place the 
samplesuperstore.csv file in the required project directory.
Step 3: Run the Python Code
Open the project in Google Colab, Jupyter Notebook, or any Python IDE and execute the code cells.
Step 4: View the Results
The program will display:
• 
• 
• 
• 
• 
• 
• 
• 
Dataset preview
Dataset information
Descriptive statistics
Unique categories
Missing value counts
Category-wise sales
Sales by category bar chart
Sales distribution histogram
5
�
� Future Enhancements
The project can be further improved by adding:
• 
• 
• 
• 
• 
• 
• 
• 
Profit analysis by category and region.
Sales analysis by month and year.
Top-selling products identification.
Regional sales comparison.
Customer segment analysis.
Correlation analysis between sales and profit.
Interactive dashboards using Power BI or Tableau.
Predictive sales forecasting using Machine Learning.
📄 Conclusion
This project demonstrates how Python can be used for data preprocessing, exploratory data analysis,
and visualization. By analyzing the Superstore dataset, useful information about category-wise sales, sales
distribution, and shipping duration can be obtained. The project provides a basic foundation for performing
more advanced business and sales analytics.
👨‍💻 Author
Sivarama Krishnan A
Project: Superstore Sales Data Analysis
Domain: Data Science and Data Analytics
Language: Python
