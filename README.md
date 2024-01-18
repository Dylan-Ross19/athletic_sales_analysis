# athletic_sales_analysis

## 1. Combine and Clean the Data

Read in CSV files into dataframes using `read_csv()` function.

Check the data to see if both dataframes share similar column names and dtypes.

Combine the dataframes by rows using `concat`. Reset the index and drop the old index column. 
This ensures the dataframe has a continuous index starting from 0.

Check if there are any null values using `.isnull().sum()` to confirm no null values.

Check each column's data type.

Convert "invoice_date" column to a datetime dtype using `pd.to_datetime()`, and confirm the change by checking its type.

## 2. Determine Which Region Sold the Most Products

Create a new dataframe showing the total products sold using `.groupby()` for region, state, and city, and `.sum()` to aggregate total units sold.

Rename the 'units_sold' to 'Total_Products_Sold' by creating a new column that has the same values as "units_sold" and then dropping "units_sold".

Sort the values by Total_Products_Sold in ascending order and display the `.tail(5)` rows.

## 3. Determine Which Region had the Most Sales

Exact same as above but using total_sales.

## 4. Determine Which Retailer had the Most Sales

Exact same as above but added the retailer in the `.groupby`.

## 5. Determine which Retailer Sold the Most Women's Athletic Footwear

Create a new dataframe based on the combined dataframe pulling the data for women athletic footwear in the products column.

Use `.groupby()` much like above.

Use `.pivot_table` with the 'invoice_date' set as the index and 'total sales' as the values, aggregated using `.aggfunc = sum`.

Use `.rename()` function to rename "total_sales" to "Total Sales".

Resample the data into daily bins using the 'resample' method using "D". Use `.sum()` to get the sum of the total sales.

## 6. Determine the Week with the Most Women's Athletic Footwear Sales

Exact same as above but used "W-Mon" to distinguish it by weekly values and set the weeks to start on Mondays.


