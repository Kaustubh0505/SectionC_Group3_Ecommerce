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
<table> <thead> <tr> <th align="left">Column</th> <th align="center">Missing %</th> <th align="center">Imputation Strategy</th> <th align="left">Business Reasoning</th> </tr> </thead> <tbody> <tr> <td><strong>Session_Duration_Avg</strong></td> <td align="center">~</td> <td align="center">Median</td> <td>Likely tracking issue; median preserves distribution</td> </tr> <tr> <td><strong>Pages_Per_Session</strong></td> <td align="center">6%</td> <td align="center">Median</td> <td>True missing values; avoids skew from extreme values</td> </tr> <tr> <td><strong>Wishlist_Items</strong></td> <td align="center">~</td> <td align="center">Median</td> <td>0 represents valid behavior; missing treated separately</td> </tr> <tr> <td><strong>Social_Media_Engagement_Score</strong></td> <td align="center">12%</td> <td align="center">Median + Missing Indicator</td> <td>0 is valid; missing not clearly behavioral</td> </tr> <tr> <td><strong>Mobile_App_Usage</strong></td> <td align="center">10%</td> <td align="center">Replaced with 0</td> <td>Likely web-only users; 0 = no app usage</td> </tr> <tr> <td><strong>Credit_Balance</strong></td> <td align="center">11%</td> <td align="center">Replaced with 0</td> <td>0 represents no available credit</td> </tr> <tr> <td><strong>Days_Since_Last_Purchase</strong></td> <td align="center">~</td> <td align="center">Median</td> <td>Data inconsistency despite purchase activity</td> </tr> <tr> <td><strong>Email_Open_Rate</strong></td> <td align="center">5%</td> <td align="center">Median</td> <td>Likely email tracking gaps</td> </tr> </tbody> </table>

Several columns contained missing values. Instead of applying a single blanket method, each column was handled based on business meaning.

- **Session_Duration_Avg** - Missing values were likely due to tracking issues (other engagement fields were filled). Replaced using median imputation to preserve distribution.

- **Pages_Per_Session** - Approximately 6% missing. Replaced using median.

- **Wishlist_Items** -Contained valid 0 values along with missing entries. Missing values replaced using median, since 0 represents real behavior.

- **Social_Media_Engagement_Score** -12% missing. Used median imputation. Considered creating a missing indicator variable since 0 is a valid score.

- **Mobile_App_Usage** - 10% missing. Replaced missing values with 0 (likely web-only users).

- **Credit_Balance** -11% missing. Replaced missing values with 0 (0 = no available credit).

- **Days_Since_Last_Purchase** - Missing values occurred despite recorded purchase activity. Treated as data inconsistency and replaced using median.

- **Email_Open_Rate** -5% missing. Replaced using median (likely tracking gaps).

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
