Task 9: House Sales Data Cleaning and Outlier Detection
Overview
This project uses Python to inspect and clean the King County house sales dataset (kc_house_data.csv). It checks data quality, prepares date-related features, calculates price-per-square-foot measures, identifies possible house-price outliers, and exports the processed dataset.
Dataset
- Input file: kc_house_data.csv
- Rows and columns in the original dataset: 21,613 rows and 21 columns
- Main information: Sale price, sale date, bedrooms, bathrooms, living area, lot area, floors, waterfront/view/condition/grade information, construction and renovation years, ZIP code, geographic coordinates, and nearby-home size measurements.
Tools and Libraries
- Python
- pandas — loading, inspecting, and cleaning tabular data
- NumPy — numeric conversions and conditional calculations
- Matplotlib — plotting
- Seaborn — creating the price box plot
Workflow
1. Load the CSV file into a pandas DataFrame.
2. Inspect descriptive statistics, dataset dimensions, column names, and missing-value counts.
3. Remove duplicate rows.
4. Convert bedrooms and bathrooms to numeric values. Values that are missing or less than or equal to zero are treated as invalid, then filled using each column's median.
5. Convert date to a datetime value and convert yr_built and yr_renovated to numeric values.
6. Create these features:
   - sale_year: year extracted from the sale date.
   - house_age: sale year minus construction year.
   - years_since_renovation: sale year minus renovation year, where a valid renovation year greater than zero exists.
7. Replace negative calculated ages with missing values.
8. Calculate price_per_sqft_living and price_per_sqft_lot when the corresponding area is greater than zero.
9. Detect possible price outliers with the Interquartile Range (IQR) rule:
   - IQR = Q3 - Q1
   - Lower bound = Q1 - 1.5 × IQR
   - Upper bound = Q3 + 1.5 × IQR
   - Mark prices outside these bounds in the valuation_outlier column.
10. Display the price bounds and number of flagged records, plot a box plot, and print selected details for flagged records.
11. Save the processed data to cleaned_house_sales.csv and display the first rows.
Output
The script writes:
- cleaned_house_sales.csv — the processed dataset, including newly created feature columns and the valuation_outlier flag.
The output file is saved in the current working directory.
How to Run
1. Keep task_9.py and kc_house_data.csv in an accessible location.
2. Install the required libraries if necessary:pip install pandas numpy matplotlib seaborn
3. Update the CSV path in task_9.py to match the location of your dataset. The current script uses a Google Colab/Drive path:df = pd.read_csv("/content/drive/MyDrive/DA/archive (2)/kc_house_data.csv")
   For local execution, if both files are in the same folder, you can use:df = pd.read_csv("kc_house_data.csv")
4. Run the script:python task_9.py
Notes and Limitations
- The script's cleaning rules are specific to this analysis and may need adjustment for other datasets.
- The IQR rule flags statistically unusual prices; a flagged value is not necessarily an error.
- The script does not remove flagged outliers. It records them in valuation_outlier for further review.
- Missing or invalid bedrooms and bathrooms values are median-imputed. Other columns are not generally imputed by this script.
- The notebook and Python script should use a dataset path that exists in the environment where they are run.
Project Files
- task_9.py — Python analysis script.
- Task_9.ipynb — Jupyter/Google Colab notebook.
- kc_house_data.csv — input dataset.
- cleaned_house_sales.csv — generated output after the script runs.
