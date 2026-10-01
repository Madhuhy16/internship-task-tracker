# Task 1 - Data Cleaning and Preprocessing

## Objective

The objective of this task is to clean and prepare a raw Superstore sales dataset using Python and Pandas.

## Dataset

Dataset used: Superstore Sales Dataset

Initial dataset size:
- Rows: 51,290
- Columns: 27

Final dataset size:
- Rows: 51,290
- Columns: 26

## Tools Used

- Python
- Pandas
- Jupyter Notebook

## Data Cleaning Steps

1. Missing Values

Checked all columns for missing values using:

python
df.isnull().sum()

Result: No missing values were found.


2. Duplicate Records

Checked for duplicate rows using:

df.duplicated().sum()

Result: No exact duplicate rows were found.


3. Date Conversion

The Order.Date and Ship.Date columns were initially stored as object.

They were converted to proper datetime format using:

df["Order.Date"] = pd.to_datetime(df["Order.Date"])
df["Ship.Date"] = pd.to_datetime(df["Ship.Date"])


4. Column Name Standardization

Column names were standardized to lowercase and underscores.

Example:

Customer.ID → customer_id
Customer.Name → customer_name
Order.Date → order_date
Shipping.Cost → shipping_cost

The transformation was performed using:

df.columns = df.columns.str.lower().str.replace(".", "_")


5. Constant Column Removal

The 记录数 column contained only the value 1 for every record.

Since it provided no useful variation, it was removed:

df = df.drop(columns=["记录数"])


6. Final Data Quality Check

A final missing-value check was performed after cleaning.

Result: 0 missing values.

Before and After
Metric         ->	      Before Cleaning 	After Cleaning
Rows           ->	         51,290	            51,290
Columns	       ->             27                  26
Missing Values ->	          0	                   0
Duplicate Rows ->             0                    0

Files Included
superstore.csv - Original raw dataset
superstore_cleaned.csv - Cleaned dataset

Task_1_Data_Cleaning.ipynb - Pandas data cleaning notebook
README.md - Task description and cleaning summary

Conclusion

The Superstore dataset was inspected and cleaned using Pandas. Date columns were converted to the appropriate datetime type, column names were standardized, and an unnecessary constant column was removed. The resulting dataset contains 51,290 rows and 26 columns and is ready for further analysis.


This README reflects the work we actually performed and the deliverables requested in the task PDF.


