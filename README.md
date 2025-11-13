# Data-Cleaning-and-Preprocessing
Clean and Prepare a Raw Dataset

### 1. Identify and Handle Missing Values

**Python (Pandas):**
python
df.isnull().sum()           # Check missing values
df.fillna(0, inplace=True)  # Replace with 0 or appropriate value
df.dropna(inplace=True)     # Remove rows with missing values

**Excel:**

* Use **Filter → Blanks** to identify missing cells.
* Fill missing values manually or with averages, or delete rows.


### 2. Remove Duplicate Rows

**Python (Pandas):**
python
df.drop_duplicates(inplace=True)

**Excel:**
Go to **Data → Remove Duplicates → Select columns to check**.


### 3. Standardize Text Values

Make sure text entries like “Male”, “male”, “MALE” are consistent.

**Python:**
python
df['Gender'] = df['Gender'].str.lower().str.strip()
df['Country'] = df['Country'].str.title()

**Excel:**
Use functions like `=LOWER(A1)` or `=PROPER(A1)` for consistency.


### 4. Convert Date Formats

Ensure all dates follow one format (e.g., **dd-mm-yyyy**).

**Python:**
python
df['Date'] = pd.to_datetime(df['Date'], format='%d-%m-%Y')

**Excel:**
Use **Text to Columns → Date → DMY** to fix formats.


### 5. Rename Column Headers

Clean and make headers uniform.

**Python:**
python
df.columns = df.columns.str.lower().str.replace(' ', '_')

**Excel:**
Edit headers manually (e.g., “Sales Amount” → “sales_amount”).


### 6. Check and Fix Data Types

Ensure numerical, categorical, and date columns are correct.

**Python:**
python
df.dtypes                 # Check data types
df['Sales'] = df['Sales'].astype(float)

**Excel:**
Use **Format Cells → Number / Date / Text** to set correct types.

THE END.
