# Home Sales
<font size="3">**Module 22 Challenge**  
**Contributors:** Cassia Yoon  
**Github link:** https://github.com/CassiaY/Home_Sales</font>  

## Project Overview  
Used SparkSQL to determine key metrics about home sales data (see questions below). Created temporary views, partitioned the data, cached and uncached a temporary table, and verified that the table was uncached at the end.  
Sample of the data:  
![sample of the data](/readme_imgs/df_sample.png)  
> Assignment prompt is found in [Module_22_Challenge.pdf](/Module_22_Challenge.pdf).  
> This project was completed using [Google Colab](/https://colab.google/).  

## Project Questions:  
1. What is the average price for a four-bedroom house sold for each year? Round off your answer to two decimal places.  
![Q1](/readme_imgs/Q1.png)  
2. What is the average price of a home for each year it was built that has three bedrooms and three bathrooms? Round off your answer to two decimal places.  
![Q2](/readme_imgs/Q2.png)  
3. What is the average price of a home for each year that has three bedrooms, three bathrooms, two floors, and is greater than or equal to 2,000 square feet? Round off your answer to two decimal places.  
![Q3](/readme_imgs/Q3.png)  
4. What is the "view" rating for homes costing more than or equal to $350,000? Determine the run time for this query (using cache, partitioning, and with neither), and round off your answer to two decimal places.  
- with neither, the runtime was `~1.107 secods`:  
![Q4](/readme_imgs/Q4.png)  
- with cacheing, the runtime was `~0.885 secods`:  
![Q4 cached](/readme_imgs/Q4_cached.png)  
- with partitioning using parquet, the runtime was `~1.122 secods`:  
![Q4 parquet](/readme_imgs/Q4_parquet.png)  
![screenshot of partitioned data](/readme_imgs/home_sales_parquet_screenshot.png)  

## Conclusion:  
Querying data from cache was the fastest method. The runtime for the partitioned data was the slowest. However, the home sales data was partitioned by year built, which was not a useful partitioning method for this particular query. Had the data been partitioned by views, the runtime might have been shorter. With smaller datasets such as these, creating a temporary cache to work from makes sense. With larger datasets, partitioning may be more appropriate.  

# Resources:
- Data for this dataset was generated by edX Boot Camps LLC, and is intended for educational purposes only.
- how to round to two decimal places in pyspark: https://www.educba.com/pyspark-round/  

# Acknowledgements
We wish to thank our teaching staff:
- Hunter Hollis
- Sam Espe
- Randy Sendek