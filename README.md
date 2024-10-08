# pandas-library
### Introduction to Pandas Library

#### **Objective:**

Students will understand the basics of the Pandas library, including DataFrame creation, handling missing data, sorting, filtering, and grouping operations.

#### **Topics Covered:**

1.  Introduction to Pandas
2.  Understanding DataFrame
3.  Creating a DataFrame for products
4.  Handling missing data (null values)
5.  Sorting and filtering data
6.  Grouping data

* * * * *

### **Introduction to Pandas**

-   **What is Pandas?**

    -   A powerful data manipulation library for Python.
    -   Provides data structures like Series and DataFrame to work with structured data.
-   **Why use Pandas?**

    -   Ease of use for data analysis.
    -   Handles missing data gracefully.
    -   Supports a variety of operations for data cleaning and transformation.

* * * * *

### **Understanding DataFrame**

-   **What is a DataFrame?**

    -   A 2-dimensional labeled data structure with columns of potentially different types (similar to a table in SQL or Excel).
    -   Data is stored in rows and columns, where each column can be of different types (e.g., integers, floats, strings).

-   **DataFrame Structure:**

    -   Rows: Individual product entries.
    -   Columns: Product attributes (e.g., ID, Name, Price, Quantity, Category).

 * * * * *

### **Creating a DataFrame for Products**

```python
import pandas as pd

# Data for products
data = {
    'ProductID': [101, 102, 103, 104, 105, 106, 107, 108, 109, 110, 
                  111, 112, 113, 114, 115, 116, 117, 118, 119, 120],
    'ProductName': ['Laptop', 'Smartphone', 'Tablet', 'Monitor', 'Keyboard', 
                    'Mouse', 'Printer', 'Scanner', 'Speaker', 'Headphones',
                    'Camera', 'Router', 'Hard Drive', 'USB Drive', 'Power Bank',
                    'Charger', 'Memory Card', 'Projector', 'Smartwatch', 'Webcam'],
    'Category': ['Electronics', 'Electronics', 'Electronics', 'Electronics', 'Accessories', 
                 'Accessories', 'Electronics', 'Electronics', 'Accessories', 'Accessories',
                 'Electronics', 'Electronics', 'Storage', 'Storage', 'Accessories',
                 'Accessories', 'Storage', 'Electronics', 'Accessories', 'Electronics'],
    'Price': [800, 600, 300, 150, 20, 15, 120, 140, 60, 80, 500, 70, 50, 15, 25, 
              10, 20, 350, 200, 45],
    'Stock': [10, 15, 12, 8, 50, 45, 7, 5, 30, 20, 9, 25, 40, 60, 18, 22, 33, 4, 10, 28],
    'Discount': [0.10, 0.15, None, 0.05, None, 0.10, None, 0.07, 0.10, None,
                 0.20, 0.05, 0.15, None, 0.05, None, 0.20, 0.10, None, 0.05]
}

# Creating the DataFrame
df = pd.DataFrame(data)

# Display the DataFrame
print(df)
```
* * * * *

### ** Handling Missing Data (Null Values)**

-   **Identify Missing Data:**
  
    `print(df.isnull())
    print(df.isnull().sum())`

-   **Filling Missing Data:**

    -   Fill missing values with a default value:

        `df['Discount'].fillna(0, inplace=True)`

-   **Dropping Rows with Missing Data:**

    -   Drop rows where any column has missing data:

        `df.dropna(inplace=True)`

* * * * *

### **Sorting and Filtering Data**

-   **Sorting by a Column:**

    -   Sort by `Price` in ascending order:

        `sorted_df = df.sort_values(by='Price')
        print(sorted_df)`

    -   Sort by `ProductName` in descending order:

        `sorted_df = df.sort_values(by='ProductName', ascending=False)
        print(sorted_df)`

-   **Filtering Data:**

    -   Filter products with price greater than $100:

        `filtered_df = df[df['Price'] > 100]
        print(filtered_df)`

    -   Filter products in the 'Accessories' category:

        `filtered_df = df[df['Category'] == 'Accessories']
        print(filtered_df)`

* * * * *

### **Grouping Data**

-   **Group by Category:**


    `grouped_df = df.groupby('Category').sum()
    print(grouped_df)`

-   **Group by Multiple Columns:**

    `grouped_df = df.groupby(['Category', 'Stock']).mean()
    print(grouped_df)`

