# SCT_DS_1
The provided script performs the following tasks related to data analysis and visualization using a population dataset:

1. **Data Loading**:
   - The script starts by loading a dataset from a CSV file (`API_SP.POP.TOTL_DS2_en_csv_v2_5871594.csv`) into a pandas DataFrame.

2. **Initial Data Inspection**:
   - It prints the first four rows of the dataset to inspect the data structure.

3. **Data Cleaning**:
   - Missing values are handled by forward-filling (`ffill`) to propagate the last valid observation forward.
   - The script checks for any remaining missing values and duplicated rows in the DataFrame.
   - Columns `Indicator Name`, `Indicator Code`, and `Country Code` are dropped as they are not needed for the analysis.

4. **Histogram Generation for Individual Columns**:
   - For each year column in the dataset (excluding `Country Name`), it generates a histogram to visualize the distribution of population values for that year. This involves:
     - Iterating over each year column.
     - Creating a histogram with 7 bins for each year column.
     - Labeling the x-axis with the year, the y-axis with 'Frequency', and setting a title indicating the histogram is for that specific year.

5. **Combined Histogram for All Year Columns**:
   - A combined histogram for all year columns is created in a single plot to visualize the overall distribution across multiple years.
   - Histograms for each year column are plotted with 7 bins and transparency (`alpha=0.5`) to distinguish between different years.
   - Labels, a title, and a legend are added to the plot.

6. **Data Sorting and Selection**:
   - The script sorts the DataFrame based on the population values for the year 1960 and selects the top 7 countries with the lowest population values for that year.

7. **Data Transformation for Visualization**:
   - The DataFrame is transformed by setting `Country Name` as the index and transposing it to facilitate plotting data values across years for each country.
   - Two separate DataFrames, `country1960T` and `country2022T`, are created but it seems the `country1960T` isn't used further in the script.

8. **Bar Plots for Each Country**:
   - For each country, a bar plot is generated to visualize data values from 1960 to 2022.
   - The script iterates over each row (each country) in the transposed DataFrame.
   - For each country, a bar plot is created with years on the x-axis, data values on the y-axis, and appropriate labels and titles.
   - The x-axis labels are rotated 90 degrees for better readability.

Overall, the script performs a comprehensive analysis of population data by cleaning the data, generating individual and combined histograms for year columns, and creating detailed bar plots for each country to visualize the population trend from 1960 to 2022.
