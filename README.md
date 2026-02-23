## E-Commerce Customer Behavior Analysis

### Project Overview

This project analyzes an e-commerce customer dataset to understand user behavior, engagement patterns, and churn trends. The goal was to clean the data, handle missing values properly, and perform exploratory analysis to identify meaningful business insights.

The dataset was obtained from Kaggle and contains 50,000 customer records with demographic, behavioral, financial, and engagement-related features. The dataset was reduced to 10,000 records for focused analysis.

Kaggle Dataset:
https://www.kaggle.com/datasets/dhairyajeetsingh/ecommerce-customer-behavior-dataset

### Objectives

- `Clean and preprocess the dataset`

- `Handle missing values using logical and data-driven decisions`

- `Analyze customer engagement behavior`

- `Explore churn-related patterns`

- `Understand customer value metrics`

### Dataset Description

The dataset includes the following categories of variables:-

- `Demographic Features`

- `Age`

- `Gender`

- `Country`

- `City`

- `Engagement & Activity Metrics`

- `Login_Frequency`

- `Session_Duration_Avg`

- `Pages_Per_Session`

- `Cart_Abandonment_Rate`

- `Wishlist_Items`

- `Email_Open_Rate`

- `Social_Media_Engagement_Score`

- `Mobile_App_Usage`

- `Product_Reviews_Written`

- `Purchase & Financial Metrics`

- `Total_Purchases`

- `Average_Order_Value`

- `Days_Since_Last_Purchase`

- `Discount_Usage_Rate`

- `Returns_Rate`

- `Lifetime_Value`

- `Credit_Balance`

Other Features:-

- `Membership_Years`

- `Customer_Service_Calls`

- `Payment_Method_Diversity`

- `Signup_Quarter`

- `Churned`

### Data Cleaning & Preprocessing
<table>
<thead>
<tr>
<th align="left">Column</th>
<th align="center">Missing Values</th>
<th align="center">Imputation / Cleaning Strategy</th>
<th align="left">Business Reasoning</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Age</strong></td>
<td align="center">513</td>
<td align="center">Replaced with Median</td>
<td>Age is demographic; median prevents distortion from extreme values</td>
</tr>
<tr>
<td><strong>Age_Group</strong></td>
<td align="center">-</td>
<td align="center">Derived Feature</td>
<td>Categorised to evaluate churn trends across age segments</td>
</tr>
<tr>
<td><strong>Session_Duration_Avg</strong></td>
<td align="center">687</td>
<td align="center">Replaced with Median</td>
<td>Likely tracking inconsistencies; median preserves behavioral distribution</td>
</tr>
<tr>
<td><strong>Pages_Per_Session</strong></td>
<td align="center">605</td>
<td align="center">Replaced with Median</td>
<td>Avoids skew caused by outlier browsing behaviour</td>
</tr>
<tr>
<td><strong>Wishlist_Items</strong></td>
<td align="center">786</td>
<td align="center">Replaced with 0</td>
<td>0 represents valid absence of wishlist activity</td>
</tr>
<tr>
<td><strong>Total_Purchases</strong></td>
<td align="center">0</td>
<td align="center">Corrected Negative Values; Removed Zero Purchase Rows</td>
<td>Negative purchases are invalid; zero purchase users removed for behavioral consistency</td>
</tr>
<tr>
<td><strong>Days_Since_Last_Purchase</strong></td>
<td align="center">575</td>
<td align="center">Replaced with Median</td>
<td>Missing despite purchase activity indicates logging inconsistency</td>
</tr>
<tr>
<td><strong>Discount_Usage_Rate</strong></td>
<td align="center">713</td>
<td align="center">Replaced with 0</td>
<td>0 implies no discount usage behaviour</td>
</tr>
<tr>
<td><strong>Returns_Rate</strong></td>
<td align="center">907</td>
<td align="center">Replaced with 0</td>
<td>Missing likely implies no returns recorded</td>
</tr>
<tr>
<td><strong>Email_Open_Rate</strong></td>
<td align="center">540</td>
<td align="center">Replaced with Median</td>
<td>Email tracking gaps; median maintains distribution</td>
</tr>
<tr>
<td><strong>Customer_Service_Calls</strong></td>
<td align="center">33</td>
<td align="center">Replaced with Median</td>
<td>Ensures minimal impact on customer support interaction analysis</td>
</tr>
<tr>
<td><strong>Product_Reviews_Written</strong></td>
<td align="center">701</td>
<td align="center">Replaced with Median</td>
<td>Missing values not necessarily behavioural absence</td>
</tr>
<tr>
<td><strong>Social_Media_Engagement_Score</strong></td>
<td align="center">1175</td>
<td align="center">Median + Derived Indicator</td>
<td>Created additional column to assess churn sensitivity to engagement</td>
</tr>
<tr>
<td><strong>Mobile_App_Usage</strong></td>
<td align="center">997</td>
<td align="center">Dropped Column</td>
<td>Highly correlated with Average Order Value = 0 for non-users; low analytical relevance</td>
</tr>
<tr>
<td><strong>Payment_Method_Diversity</strong></td>
<td align="center">492</td>
<td align="center">Replaced with Median</td>
<td>Prevents distortion in payment behaviour patterns</td>
</tr>
<tr>
<td><strong>Credit_Balance</strong></td>
<td align="center">1107</td>
<td align="center">Replaced with 0</td>
<td>0 represents absence of available credit</td>
</tr>
</tbody>
</table>


Several columns contained missing values. Instead of applying a single blanket method, each column was handled based on business meaning.
* **Session_Duration_Avg** – Missing values were likely due to tracking inconsistencies (other engagement metrics were available). Replaced using median imputation to preserve the original behavioral distribution.

* **Pages_Per_Session** – Approximately 605 missing values observed. Replaced using median to avoid skew from extreme browsing behaviour.

* **Wishlist_Items** – Contained valid 0 values representing absence of wishlist activity. Missing values were replaced with 0 to maintain behavioral consistency.

* **Social_Media_Engagement_Score** – 1175 missing values identified. Replaced using median imputation. Additionally, a derived indicator column was created to evaluate the impact of social media engagement on churn behaviour.

* **Mobile_App_Usage** – 997 missing values observed. Due to its strong association with zero Average_Order_Value among non-users and limited analytical relevance, the column was dropped from further analysis.

* **Credit_Balance** – 1107 missing values present. Replaced missing values with 0, assuming absence of available credit.

* **Days_Since_Last_Purchase** – Missing values occurred despite recorded purchase activity. Treated as data inconsistency and replaced using median.

* **Email_Open_Rate** – 540 missing values identified. Replaced using median to address potential email tracking gaps.


### Exploratory Data Analysis (EDA)

- Pivot tables were created to compare churned (1) and active (0) users across engagement, purchasing behavior, demographics, and geography.

- The Churned column was used as the primary target variable to identify behavioral changes before customers leave the platform and to determine retention priorities.

### Areas of Analysis

- Engagement behavior comparison (session duration, login frequency, browsing depth, email engagement, social engagement)

- Purchasing behavior trends (purchase frequency, order value, recency, cart abandonment, discount usage)

- Demographic segmentation (gender and age distribution)

- Geographic segmentation (country-level churn exposure)

- Data quality transparency using derived variable Social_Score_Missing

### Key Insights

- Churned customers showed consistently lower login frequency, session duration, and pages per session, indicating early disengagement.

- Higher Days_Since_Last_Purchase strongly aligned with churn risk, confirming recency as a major predictor.

- Churned users had lower total purchases, reducing overall revenue contribution.

- Higher cart abandonment rates and heavy discount dependency were linked to high-risk segments.

- Lower email open rates and social media engagement scores signaled weakening brand connection.

- Certain geographic regions showed higher churn exposure, helping prioritize retention strategies.

### Tools Used

- `Excel / Google Sheets (data cleaning and pivot analysis)`

- `Median imputation techniques`

- `Exploratory data analysis methods`

### Learning Outcomes

- Applied logical, business-driven missing value handling

- Understood the importance of domain knowledge before preprocessing

- Evaluated how imputation impacts analysis quality

- Identified engagement patterns linked to churn

- Structured and documented a complete data analysis project
