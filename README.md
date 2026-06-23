# Data-Engineering-Pandas
# Pandas Workbook for Data Engineering

This Jupyter Notebook (`Pandas_Workbook_SJ.ipynb`) is a comprehensive, hands-on guide to using **pandas** for data engineering tasks. It covers everything from basic DataFrame operations to advanced data manipulation, including loading data from multiple sources, cleaning, transformation, aggregation, and exporting.

The workbook is designed for interns or junior data engineers who need to build a solid foundation in pandas before moving on to production‑grade pipelines. It contains **35+ sections** with working code examples and explanations.

---

## Notebook Contents

The notebook is organised into the following sections:

| Section | Topic |
|---------|-------|
| 1 | Creating a DataFrame from a dictionary |
| 2 | Loading data from CSV (`read_csv`) |
| 3 | Data exploration – `head`, `tail`, `shape`, `columns`, `info`, `describe`, `dtypes` |
| 4 | Data type conversion (e.g., `to_datetime`) |
| 5 | Manipulating column names – direct assignment vs `rename` |
| 6 | Difference between DataFrame and Series |
| 7 | Changing the index (`set_index`) |
| 8 | Resetting the index (`reset_index`) |
| 9 | Selection using `iloc` (index‑based) and `loc` (label‑based) |
| 10 | Sorting by index (`sort_index`) and by values (`sort_values`) |
| 11 | Multi‑column sorting |
| 12 | Data filtering with `loc` and boolean conditions |
| 13 | Multi‑condition filtering (`&` and &#124; ) |
| 14 | Inverse filtering (`~`) |
| 15 | Filtering based on datetime columns |
| 16 | Adding a new column |
| 17 | Deleting a column (`drop`) |
| 18 | Updating column values |
| 19 | Conditional updates using `loc` |
| 20 | Applying transformations with `.apply()` and custom functions |
| 21 | Series string methods (`.str.upper()`, `.str.startswith()`, etc.) |
| 22 | Handling missing values (`isnull`, `dropna`, `fillna`) |
| 23 | Handling duplicates (`drop_duplicates`) |
| 24 | Extracting date parts (`.dt.year`, `.dt.month`, `.dt.day_name()`) |
| 25 | Basic aggregations (`sum`, `mean`, `max`, `min`, `count`, `nunique`, `unique`) |
| 26 | Group‑by aggregations (`.groupby()`) |
| 27 | Multi‑aggregation using `.agg()` – two methods |
| 28 | Pivot tables (`pivot_table`) |
| 29 | Joins / merges (`pd.merge` – inner, left, right, outer, cross) |
| 30 | Concatenation (`pd.concat`) |
| 31 | Writing DataFrames to files (CSV, Excel, JSON, Parquet) |
| 32 | Reading DataFrames from files (CSV, Excel, JSON, Parquet) |
| 33 | Reading from MySQL using `sqlalchemy` and `create_engine` |
| 34 | Writing to MySQL (`to_sql` with `replace` / `append` / `fail`, and truncation with `text`) |
| 35 | **Mini ETL Project** – Extract from JSON, Transform into DataFrames, Load to MySQL |

---

## Topics Covered in Detail

### 1. Creating and Loading Data
- **Creating a table** – building a DataFrame from a Python dictionary.
- **Loading existing data** – using `pd.read_csv()` to import external CSV files.

### 2. Data Exploration
- **First/last rows** (`head`, `tail`)
- **Shape and columns** (`shape`, `columns`)
- **Summary information** (`info`, `dtypes`, `describe`)

### 3. Indexing and Selection
- **Difference between DataFrame and Series** (single column vs. full table).
- **Changing index** – `set_index` and `reset_index`.
- **Position‑based selection** – `iloc`.
- **Label‑based selection** – `loc`.

### 4. Sorting
- **Sort by index** – `sort_index`.
- **Sort by column values** – `sort_values` (single and multiple columns).

### 5. Filtering
- **Single‑condition filtering** with boolean masks.
- **Multiple conditions** using `&` (and) and `|` (or).
- **Inverse filtering** with `~`.
- **Filtering on datetime columns** (e.g., orders after a specific date).

### 6. Column Operations
- **Adding new columns** – direct assignment.
- **Deleting columns** – `drop`.
- **Updating existing columns** – direct or conditional updates.
- **Conditional updates** using `loc` with multiple conditions (grouping logic).

### 7. Transformations
- **Applying functions** – `.apply()` with custom Python functions.
- **Series string methods** – `.str.upper()`, `.str.startswith()`, etc.

### 8. Data Cleaning
- **Missing values** – detecting (`isnull`), counting, dropping (`dropna`), and filling (`fillna`).
- **Duplicates** – `drop_duplicates` with subsets and `keep` parameters.

### 9. Date/Time Handling
- **Converting to datetime** – `pd.to_datetime` with explicit formats.
- **Extracting components** – `.dt.year`, `.dt.month`, `.dt.day`, `.dt.day_name()`.

### 10. Aggregations and Grouping
- **Basic aggregations** – `sum`, `mean`, `max`, `min`, `count`, `nunique`, `unique`.
- **Group‑by** – `.groupby()` for single and multiple columns.
- **Multiple aggregations** – two approaches using `.agg()`:
  - List of functions on a single column.
  - Dictionary mapping columns to functions.

### 11. Pivot Tables
- **Creating pivot tables** – `pivot_table` with `index`, `columns`, `values`, and `aggfunc`.

### 12. Merging and Concatenating
- **SQL‑style joins** – `pd.merge` with `how='inner'`, `'left'`, `'right'`, `'outer'`, `'cross'`.
- **Concatenation** – `pd.concat` for stacking rows.

### 13. I/O Operations
- **Writing to files** – CSV, Excel, JSON, Parquet.
- **Reading from files** – CSV, Excel, JSON, Parquet.

### 14. Database Integration
- **Reading from MySQL** – using `sqlalchemy.create_engine` and `pd.read_sql`.
- **Writing to MySQL** – `df.to_sql` with `if_exists` options (`replace`, `append`, `fail`).
- **Truncating tables** – using `text` and `conn.execute()`.

### 15. Mini ETL Project
- **Extract** – loading a nested JSON file (`orders_etl.json`) using Python’s `json` module.
- **Transform** – flattening the nested structure into three normalized DataFrames (orders, products, customers) with deduplication and basic preprocessing.
- **Load** – writing the cleaned DataFrames to a MySQL database using `to_sql` with `replace` strategy, ready for downstream analytics.

---

## Topics for Further Study (Not Covered)

While the workbook provides a solid foundation, the following topics were left out but are crucial for advanced data engineering work. We recommend diving deeper into these areas:

### Advanced Data Cleaning
- **Outlier detection** – using the IQR method to identify extreme values.
- **Outlier capping / winsorizing** – clipping outliers instead of removing them.
- **Categorical encoding** – converting strings to numeric codes (`cat.codes`) for ML or storage.
- **One‑hot encoding** – creating dummy variables with `pd.get_dummies`.
- **Regular expressions** – using `.str.extract()`, `.str.contains()`, and `.str.replace()` with regex for messy text.
- **Handling inconsistent date formats** – `pd.to_datetime` with `infer_datetime_format` or explicit format strings.
- **Timezone localisation and conversion** – `.dt.tz_localize` and `.dt.tz_convert`.
- **Selective column renaming** – using a dictionary in `df.rename()`.

### Working with Large Datasets (Optimisation)
- **Memory profiling** – `df.memory_usage(deep=True)` to identify memory hogs.
- **Integer and float downcasting** – reducing bit‑width with `pd.to_numeric(..., downcast=...)`.
- **Categorical dtype for strings** – converting low‑cardinality object columns to `category`.
- **Chunked reading** – processing huge CSV files in batches with `chunksize`.
- **Query optimisation** – using `df.query()` for faster filtering.
- **Efficient file formats** – Parquet and Feather (faster, compressed).
- **Vectorised JSON flattening** – using `pd.json_normalize()` instead of manual loops.
