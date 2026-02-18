Data Cleaning

This section documents the preprocessing and data cleaning steps performed to ensure data quality, consistency, and suitability for analysis and modeling.

1. Age Column

Outlier Removal:
An extreme outlier value (e.g., 150) was identified and removed from the dataset.

Post-cleaning Range:

Min: 5

Max: 75

Missing Value Treatment:
Missing values were imputed using the median of the column.

Reason:
The median was chosen to minimize skewness and reduce the impact of extreme values.

2. Gender Column

This is a categorical column.

No missing values were found.

Gender	Count
Male	4,699
Female	5,302
3. Session Duration

Missing Values: 687

Mean: 27.6

Median: 26.8

Range: 1 – 69

Missing values were imputed using the median of the column.

4. Pages per Session

Missing Values: 605

Mean: 8.7

Median: 8.5

Missing values were imputed using the median.

5. Wishlist Items

Missing Values: 786

Missing values were replaced with 0.

Assumption:
Missing entries indicate no wishlist activity.

6. Total_Purchase

Negative Values Found: 15

Mean: 13

Decimal Values: 2,272

Cleaning Steps:

Replaced negative values with 0 (total purchases cannot be negative).

Converted decimal values to integers using the floor function.

7. Days_since_last_purchase

Missing Values: 573

Mean: 29

Range: 0 – 287

Missing values were replaced with the mean of the column.

8. Discount_Usage_Rate

Missing Values: 711

Mean: 41.9

Missing values were replaced with 0.

Assumption:
Missing values imply no discount usage.

9. Returns_Rate

Missing Values: 905

Mean: 6.62

Missing values were replaced with 0.

10. Email_Open_Rate, Customer_Service_Calls, Product_Reviews_Written
Column	Missing Values
Email_Open_Rate	538
Customer_Service_Calls	31
Product_Reviews_Written	699

Missing values were replaced with the median of their respective columns.

11. Social_Media_Engagement_Score

Missing Values: 1,174

A new column named Social_Score_missing was created to track missing values.

Purpose:
To analyze whether missing engagement scores correlate with churn rate and to assess how social media engagement affects customer behavior.

12. Payment_Method_Diversity

Missing Values: 490

Mean: 2

Range: 1 – 5

Missing values were replaced with the mean, as the affected rows showed average order values.

13. Credit_Balance

Missing Values: 1,105

Mean: 1,965

Range: 0 – 7,197

Missing values were replaced with 0.

Reason:
Using the mean would artificially inflate credit balances and introduce bias into the dataset.

Summary of Cleaning Strategy

Median imputation was used for skewed numerical features.

Mean imputation was applied where the distribution was relatively stable.

Zero imputation was used where missing values logically indicated absence of activity.

Invalid negative values were corrected.

Indicator features were created to preserve missing-data insights.