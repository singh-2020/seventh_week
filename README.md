📌 Description

The ETL script does the following:

1. Read CSV files from each folder (`CUST_MSTR`, `PROD_MSTR`, `TXN_DATA`)
2. Extract date from filename using regular expressions
3. Drop unnecessary columns like file name
4. Truncate Hive tables
5. Load the data into Hive-managed tables (`append` mode)


⚙️ Dependencies

- Python 3.7+
- Apache Spark 3.x with Hive support
- Java 8 or 11
- PySpark (`pip install pyspark`)
- Hive metastore (optional if using embedded)



📝 Sample Filenames

| Folder     | Filename Pattern         |
| ---------- | ------------------------ |
| CUST\_MSTR | `CUST_MSTR_YYYYMMDD.csv` |
| PROD\_MSTR | `PROD_MSTR_YYYYMMDD.csv` |
| TXN\_DATA  | `TXN_DATA_YYYYMMDD.csv`  |

Date (`YYYYMMDD`) is extracted from filenames to populate a `Date` column.


📦 Output Tables (Hive)

| Table Name  | Description            |
| ----------- | ---------------------- |
| `CUST_MSTR` | Customer master data   |
| `PROD_MSTR` | Product master data    |
| `TXN_DATA`  | Transaction-level data |


🧪 Testing

Mock data can be created manually or by using the provided sample CSVs. Use consistent date-based filenames for proper loading.


📚 License

This project is for educational and prototype purposes.
