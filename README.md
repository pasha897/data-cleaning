# data-cleaning
File Loaded: Data is read from caller_list_raw_data.xlsx into a DataFrame (df_raw).
The notebook displays df_raw.head() and df_raw.info(), providing an overview of column names, data types, and non-null counts.
Duplicates: Any duplicate rows are removed via df.drop_duplicates(inplace=True).
Index Reset: After deduplication, index is reset using df.reset_index(drop=True) to ensure clean ordering.

Handling Missing or Erroneous Data
1) The notebook identifies missing values with df.isnull().sum().
2) Depending on the column:
    Empty strings or NaNs in essential fields (like Name, Phone) are either replaced or marked for removal.
    Date fields are converted to datetime, with invalid dates handled (either dropped or corrected).
    Numerical fields are checked and converted as needed; outliers may be filtered out.
