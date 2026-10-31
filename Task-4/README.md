Shopify Stock Data Analysis
Project Overview
This project uses Python to analyze Shopify historical stock data. It explores stock prices, daily price changes, daily returns, trading volume, unusual high-volume trading days, and return statistics. It also creates visualizations to show price and volume trends and the distribution of daily returns.
Objectives
- Load and inspect the Shopify stock dataset.
- Convert the date column into a datetime format.
- Check for missing values and remove incomplete rows.
- Remove duplicate records and sort the data by date.
- Calculate daily price change (Daily Delta).
- Calculate daily percentage return.
- Analyze average, maximum, and minimum trading volume.
- Identify days with unusually high trading volume.
- Calculate mean, variance, and standard deviation of daily returns.
- Visualize closing prices, trading volume, and daily returns.
Project Files
- shopify_stock(1).ipynb – Jupyter Notebook containing the analysis.
- shopify_stock(1).py – Python script containing the analysis.
- shopify_stock(1).csv – Dataset used in the project.
Dataset Description
The supplied CSV dataset contains 2,469 rows and 7 columns.
Column	Description
date	Date of the stock record
open	Opening stock price
high	Highest stock price
low	Lowest stock price
close	Closing stock price
adj_close	Adjusted closing stock price
volume	Number of shares traded


Technologies and Libraries
- Python – programming language.
- Pandas – loading, cleaning, sorting, and analyzing tabular data.
- NumPy – numerical computing (imported in the supplied code).
- Matplotlib – creating line charts.
- Seaborn – creating the daily-return histogram.
Installation
Install the required packages:
pip install pandas numpy matplotlib seaborn jupyter
How to Run
Option 1: Google Colab
1. Open shopify_stock(1).ipynb in Google Colab.
2. Upload the CSV dataset.
3. Update the CSV filename in the loading statement if necessary.
4. Run the notebook cells from top to bottom.
Option 2: Run Locally
1. Place the notebook, Python script, and CSV file in the same folder.
2. In the script, make sure the CSV loading statement uses the actual filename. For the uploaded file, use:
df = pd.read_csv("shopify_stock(1).csv")
3. Install the required libraries using the command above.
4. Run the script:
python "shopify_stock(1).py"
Analysis Performed
1. Load and Understand the Data
The project loads the CSV file with Pandas and examines:
- The first few records using head().
- The number of rows and columns using shape.
- Column names, data types, and non-null counts using info().
- Descriptive statistics using describe().
2. Date Conversion
The date column is converted into a datetime format using pd.to_datetime() with UTC enabled.
3. Data Cleaning
- Checks missing values using isnull().sum().
- Removes rows containing missing values using dropna().
- Removes duplicate records using drop_duplicates().
- Sorts the records by date using sort_values().
4. Daily Delta
The daily price change is calculated as:
Daily_Delta = close - open
This shows the difference between the closing and opening prices for each trading day.
5. Daily Return
The daily percentage return is calculated as:
Daily_Return = ((close - open) / open) * 100
The calculated date, opening price, closing price, daily delta, and daily return are displayed.
6. Trading Volume Analysis
The project calculates:
- Average trading volume.
- Maximum trading volume.
- Minimum trading volume.
It then sets an unusual-volume threshold at twice the average volume:
threshold = 2 * average_volume
Records with volume greater than this threshold are selected as anomalous trading days and displayed with their date, prices, daily delta, daily return, and volume.
7. Daily Return Statistics
The project calculates three statistical measures for Daily_Return:
- Mean – average daily return.
- Variance – measure of how spread out the returns are.
- Standard deviation – measure of variation in the returns.
8. Data Visualizations
- Shopify Closing Price Trend: a line chart showing closing price over time.
- Shopify Trading Volume Trend: a line chart showing trading volume over time.
- Shopify Daily Return Distribution: a histogram showing the distribution of daily percentage returns.
Expected Output
When the code runs successfully, it displays:
- Dataset preview, shape, information, and descriptive statistics.
- Missing-value counts.
- Calculated daily delta and daily return.
- Trading-volume statistics and unusually high-volume trading days.
- Mean, variance, and standard deviation of daily returns.
- Closing-price trend, trading-volume trend, and daily-return distribution charts.
Important Notes About the Supplied Code
1. The supplied code reads shopify_stock.csv, but the uploaded dataset is named shopify_stock(1).csv. Update the filename in pd.read_csv() to match the actual file.
2. The final histogram uses sns.histplot(), but the supplied notebook and Python script do not import Seaborn. Add this line with the other imports before running the complete analysis:
import seaborn as sns
3. The script calculates minimum_volume, but it does not print that value. Add print("Minimum Volume:", minimum_volume) if you want it displayed.
4. The volume chart is saved as chart.png in the supplied code. The output location depends on the folder from which the script or notebook is run.
Conclusion
This project demonstrates basic stock-market data analysis using Python. It applies data inspection and cleaning, calculates daily price changes and percentage returns, examines trading volume, identifies unusually high-volume days using a simple threshold, and presents the results through statistical summaries and charts.
