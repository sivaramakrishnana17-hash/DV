Data Visualization – Superstore Sales Analysis
Project Overview
This project performs exploratory data analysis and visualization on the Sample Superstore dataset using Python. It examines sales, profit, discounts, delivery time, and relationships between numerical variables.
Objectives
- Load and inspect the Superstore dataset.
- Explore dataset structure and descriptive statistics.
- Convert order and shipping dates into datetime format.
- Calculate delivery time in days.
- Examine missing values and product categories.
- Visualize sales and profit using bar plots, histograms, and box plots.
- Explore the relationship between discounts and profit.
- Calculate and visualize correlations between numerical columns.
Files
- Task_1_BDA_(2).ipynb – Jupyter/Google Colab notebook containing the analysis.
- task_1_bda_(2).py – Python script containing the same analysis.
- samplesuperstore - samplesuperstore(1).csv – Dataset used by the project.
Dataset
The supplied CSV contains 10,194 rows and 21 columns. Its fields include order and shipping details, customer and location information, product category and sub-category, sales, quantity, discount, and profit.

Important columns used in the analysis:
- Order Date and Ship Date
- Category
- Sales
- Profit
- Discount
Technologies and Libraries
- Python
- Pandas – data loading, cleaning, grouping, and analysis
- NumPy – numerical computing
- Matplotlib – plotting
- Seaborn – statistical visualizations
- Jupyter Notebook / Google Colab – running the notebook
Installation
Install the required libraries:
pip install pandas numpy matplotlib seaborn jupyter
How to Run
Option 1: Google Colab
1. Open Task_1_BDA_(2).ipynb in Google Colab.
2. Upload the CSV dataset to the Colab session.
3. Make sure the CSV filename matches the filename used in the notebook, or update the pd.read_csv() path.
4. Run the notebook cells from top to bottom.
Option 2: Run the Python Script Locally
1. Keep the Python script and CSV dataset in the same folder.
2. In task_1_bda_(2).py, change the CSV loading line to the actual local filename, for example:
df = pd.read_csv("samplesuperstore - samplesuperstore(1).csv")
3. Run the script:
python "task_1_bda_(2).py"
Analysis Performed
1. Data Loading and Inspection
- Reads the CSV file using Pandas.
- Displays the first rows with head().
- Checks column data types and non-null counts using info().
- Displays descriptive statistics using describe().
2. Date Conversion and Delivery Days
- Converts Order Date and Ship Date to datetime values.
- Creates a Delivery Days column by subtracting the order date from the ship date.
3. Category and Missing-Value Checks
- Lists the unique values in the Category column.
- Checks missing values in each column.
- Groups records by category and calculates total sales.
4. Visualizations
- Sales by Category – Bar Plot: compares total sales across categories.
- Sales Distribution – Histogram: displays the distribution of sales values.
- Profit by Category – Bar Plot: compares profit across categories.
- Sales by Category – Bar Plot: visualizes sales by category.
- Profit Distribution – Box Plot: shows the distribution, median, variation, and potential outliers in profit.
- Profit Variation Across Categories – Box Plot: compares profit distributions across categories.
- Discount vs Profit – Scatter Plot: explores how discount values relate to profit.
- Correlation Heatmap: displays correlations among numerical columns.
Expected Output
When the notebook or script runs successfully, it displays dataset previews and information, descriptive statistics, category and missing-value checks, calculated delivery days, and the plots listed above.
Notes
- The dataset must be available at the path specified in pd.read_csv().
- The notebook and script currently use /content/samplesuperstore.csv, which is a Google Colab-style path. Update it when running locally.
- The project code creates visualizations; it does not save the plots to image files.
- This README describes the operations present in the supplied code and does not state specific analytical conclusions.
