## LP3-Regression_Project
## A time series project
## Project Title: 
### `Sales Forecasting and Inventory Optimization For Ecuador Retail Businesses`
## Project Understanding and Description:
Develop a time series forecasting model to predict retail sales for different stores in Ecuador.

Integrate external factors like oil prices and holiday events to enhance the accuracy of the forecasts.

Explore how optimized sales forecasting can lead to better inventory management and cost savings.`

### 1. `Business Objective:`

To improve sales forecasting and optimize inventory management for retail stores in Ecuador 

by leveraging historical sales data, oil prices, and holiday information.

####       `Anticipated Business Impact:`
(i) Reduce overstock and stockouts, leading to increased customer satisfaction.

(ii) Optimize inventory levels, improving cash flow and reduce holding costs.

(iii) Enhance operational efficiency in responding to seasonality and holiday demand.

### 2. `Assess Situation:`

####   (i) `Resource Availability:`

Access to historical sales data, oil prices, and holiday information.

A team of skilled data analysts and data scientists.

Adequate computational resources for data processing, analysis and modeling.

####   (ii) `Project Requirements:`

Develop a time series forecasting model by making use of available data.

Integrate data from:

(a) 'oil', 'holidays_events', 'stores', and 'transactions'; 

These datasets contain the relevant information required for time series forecasting, 

such as sales transactions, store information, and external events that may impact the time series.

(b) 'sample_submission' and 'test': These datasets will be useful for evaluating the model's performance. and

(c) 'train': This is the main training dataset for building and training the forecasting model.

####   (iii) `Address missing data and ensure data quality.`
Implement visualization for exploratory data analysis.

Evaluate model performance using relevant metrics.

####   (iv) `Risks and Contingencies:`

Risks that may occur include inaccurate or incomplete data, and potential challenges in modeling complex retail sales patterns.

Possible contingencies that we might incur are; thorough data cleaning, exploration, and collaboration with domain experts for better understanding.

####   (v) `Cost-Benefit Analysis:`

Costs expected include data storage, computational resources, and human resources.

Benefits include improved sales forecasting, optimized inventory, and potential revenue increase.

### 3. `Data Mining Goals:`

(i) To develop a time series forecasting model for retail sales.

(ii) Explore the impact of oil prices and holidays on sales.

(iii) Identify patterns and trends in the data to improve decision-making.

(iv) Optimize model parameters for accurate sales predictions.

### 4.  `Project Plan:`
#### (a) `Phase 1: Data Preparation`

Clean and preprocess data (handle missing values, outliers, and format issues).
Merge relevant datasets ('oil', 'holidays_events', 'stores', and 'transactions').

#### (b) `Phase 2: Exploratory Data Analysis (EDA)`
Visualize time series data, identify seasonality and trends.
Explore the relationships between sales, oil prices, and holidays.

#### (c) `Phase 3: Model Development`
Choose and implement a time series forecasting model (e.g., SARIMA, LSTM).
Train the model on historical data.

#### (d) `Phase 4: Model Evaluation`
Evaluate model performance on a test set.
Fine-tune hyperparameters for optimal results.

#### (e) `Phase 5: Deployment`
Deploy the model for real-time predictions.
Monitor and update the model as needed.

#### (f) `Tools and Technologies:`

Python (Pandas, NumPy, Scikit-Learn, TensorFlow or PyTorch for modeling).

Jupyter Notebooks for code development and documentation.

Data visualization libraries (Matplotlib, Seaborn).

#### (g) `Methodology`
To achieve the objectives, we will follow a structured approach:

Data Exploration: Thoroughly explore the provided datasets to understand the available features, their distributions, and relationships. This step will provide initial insights into the store sales data and help identify any data quality issues.

Data Preparation: Handle missing values, perform feature engineering, and encode categorical variables as necessary. This step may involve techniques like imputation, scaling, and one-hot encoding.

Time Series Analysis: Analyze the temporal aspects of the data, including trends, seasonality, and potential outliers. This analysis will provide a deeper understanding of the underlying patterns in store sales over time.

Model Selection and Training: Select appropriate time series forecasting models and train them using the prepared data. Consider incorporating external factors like promotions, holidays, and oil prices, if available, to enhance the forecasting accuracy.

Model Evaluation: Evaluate the trained models using appropriate metrics, such as mean absolute error (MAE), root mean squared error (RMSE), or mean absolute percentage error (MAPE). Assess the models' performance and identify the most accurate and reliable forecasting model.

Model Deployment and Forecasting: Deploy the chosen model to predict store sales for future time periods, leveraging the provided test dataset. Generate forecasts for the target period and assess the model's ability to capture the sales patterns accurately.

By following this methodology, we aim to provide valuable insights to the telecom company and develop a reliable predictive model for customer churn.

### 5. `Hypothesis formation`

`Null Hypothesis (H0):` Seasonal variations, including holiday events, promotions and oil prices have no significant impact on retail sales.

`Alternative Hypothesis (H1):` Seasonal variations, including holiday events, promotions and oil prices significantly influence retail sales.

### 6. `Analytical Questions`
1. Which dates have the lowest and highest sales for each year?
2. Did the earthquake impact sales?
3. Are sales affected by promotions, oil prices and holidays?. 
4. What analysis can we get from the date and its extractable features?
5. What is the difference between RMSLE, RMSE, MSE (or why is the MAE greater than all of them?)

### `Issues with the data` 

(a)  Inconsistent Date Formats:
How to deal with:

Convert the 'date' column to a consistent datetime format.

(b) Inaccurate or Incomplete External Data:
Approach:
Review and clean external data sources, addressing missing values or inaccuracies.

(c) Missing values: (43 null values in oil data before merge) We will fill the missing values using appropriate methods such as forward fill or backward fill.

(d) More missing values after merging
(e) Outliers: We will identify and remove the outliers by analyzing the data distribution and using appropriate statistical techniques.

### Import and Load Necessary Libraries

![image](https://github.com/NginaMuinde/LP3-Regression-Project/assets/149095447/ad813595-be69-4cdf-b905-b2f1e087b355)

## Data Loading

### Establish connections to SQL Server

![image](https://github.com/NginaMuinde/LP3-Regression-Project/assets/149095447/8b8974b1-b9a0-4574-bdb3-155030cdc287)

## Load all Datasets 

![image](https://github.com/NginaMuinde/LP3-Regression-Project/assets/149095447/4386d09e-0d89-449a-b7be-9381c3e8a64d)

![image](https://github.com/NginaMuinde/LP3-Regression-Project/assets/149095447/210eb7dc-f81d-4df4-be5d-63d9ff71c29d)

# Exploratory Data Analysis (EDA), Data Preprocessing & Cleaning 

## Understanding the Datasets

![image](https://github.com/NginaMuinde/LP3-Regression-Project/assets/149095447/4db18703-9613-4c96-8c59-6453e7c5f2a5)

The Holiday Events dataset contains 350 rows and 6 columns. This dataset provides information about various holidays and events.

The Oil dataset consists of 1,218 rows and 2 columns. This dataset includes information about the daily price of oil.

The Stores dataset contains 54 rows and 5 columns. This dataset provides details about different stores, such as their locations, types, and clusters.

The Transactions dataset contains 83,488 rows and 3 columns. This dataset contains information about the number of transactions made at each store on specific dates.

The train dataset contains 3,000,888 rows and 6 columns while the test dataset contains 28,512 rows and 5 columns.

The train dataset is significantly larger than the test dataset in terms of the number of rows. This is expected, as the train dataset is usually larger to provide sufficient data for model training.

![image](https://github.com/NginaMuinde/LP3-Regression-Project/assets/149095447/bf34e86b-3105-4451-99e1-0eb894536b28)

![image](https://github.com/NginaMuinde/LP3-Regression-Project/assets/149095447/868395a0-c1bb-4f49-a377-5b2686e67ead)

![image](https://github.com/NginaMuinde/LP3-Regression-Project/assets/149095447/121aa852-3f17-48ec-9da9-b17fd34f7485)

![image](https://github.com/NginaMuinde/LP3-Regression-Project/assets/149095447/f2618825-e246-4e7f-a7c8-1d89bfd2baf5)

##### Features and descriptions of the datasets


| Feature            | Description                                                                                                      |
| ---------------- | ---------------------------------------------------------------------------------------------------------------- |
| store_nbr           | identifies the store at which the products are sold.                                                                       |
| family    | identifies the type of product sold.                                                                    |
| sales          | gives the total sales for a product family at a particular store at a given date. Fractional values are possible since products can be sold in fractional units (1.5 kg of cheese, for instance, as opposed to 1 bag of chips).                                                              |
| onpromotion       | gives the total number of items in a product family that were being promoted at a store at a given date.         


##### The Holiday Events Dataset:
- The dataset contains 350 entries and 6 columns: 'date', 'type', 'locale', 'locale_name', 'description', and 'transferred'.
- The "date" column in the dataset is of type object. It needs to be converted to a datetime data type for further analysis.

##### The Oil Dataset:
- The dataset contains 1,218 entries has 2 columns: 'date' and 'dcoilwtico'.
- The "date" column in the dataset is of type object. It needs to be converted to a datetime data type for further analysis.
- The 'dcoilwtico' column has 1,175 non-null values, indicating that there are some missing values in this column.

##### The Stores dataset:
- The dataset contains 54 entries and 5 columns: 'store_nbr', 'city', 'state', 'type', and 'cluster'.

##### The Transactions dataset:
- The dataset contains 83,488 entries and 3 columns: 'date', 'store_nbr', and 'transactions'.
- The "date" column in the dataset is of type object. It needs to be converted to a datetime data type for further analysis.


##### The Train and Test datasets:
- The train dataset contains 3,000,888 entries and 6 columns: 'id', 'date', 'store_nbr', 'family', 'sales', and 'onpromotion'.
- The test dataset contains 28,512 entries and 5 columns: 'id', 'date', 'store_nbr', 'family', and 'onpromotion'.
- The "date" column in both datasets are of type object. It needs to be converted to a datetime data type for further analysis.
- As expected, the test dataset does not have the "sales" column. This column is not needed because 'sales' is the variable we want to predict. The goal is to use the trained model to predict or forecast the sales in the test data based on the other available features.

### Transform the 'date' column to datetime format

Check the date ranges of the datasets

![image](https://github.com/NginaMuinde/LP3-Regression-Project/assets/149095447/cb9f4304-9bf5-4e44-8ca2-678e0148a189)

![image](https://github.com/NginaMuinde/LP3-Regression-Project/assets/149095447/052651c2-8461-4568-9e62-07e5eaa0dfd0)

The 'date' columns in all datasets are formatted correctly.

###  Summary statistics of the datasets


Holiday events dataset summary statistics:
---------------------------------------------
                                date
count                            350
mean   2015-04-24 00:45:15.428571392
min              2012-03-02 00:00:00
25%              2013-12-23 06:00:00
50%              2015-06-08 00:00:00
75%              2016-07-03 00:00:00
max              2017-12-26 00:00:00
============================================================

Oil dataset summary statistics:
---------------------------------------------
                      date   dcoilwtico
count                 1218  1175.000000
mean   2015-05-02 12:00:00    67.714366
min    2013-01-01 00:00:00    26.190001
25%    2014-03-03 06:00:00    46.405001
50%    2015-05-02 12:00:00    53.189999
75%    2016-06-30 18:00:00    95.660000
max    2017-08-31 00:00:00   110.620003
std                    NaN    25.630476
============================================================

Stores dataset summary statistics:
---------------------------------------------
       store_nbr    cluster
count  54.000000  54.000000
mean   27.500000   8.481481
std    15.732133   4.693395
min     1.000000   1.000000
25%    14.250000   4.000000
50%    27.500000   8.500000
75%    40.750000  13.000000
max    54.000000  17.000000
============================================================

Transactions dataset summary statistics:
---------------------------------------------
                                date     store_nbr  transactions
count                          83488  83488.000000  83488.000000
mean   2015-05-20 16:07:40.866232064     26.939237   1694.602158
min              2013-01-01 00:00:00      1.000000      5.000000
25%              2014-03-27 00:00:00     13.000000   1046.000000
50%              2015-06-08 00:00:00     27.000000   1393.000000
75%              2016-07-14 06:00:00     40.000000   2079.000000
max              2017-08-15 00:00:00     54.000000   8359.000000
std                              NaN     15.608204    963.286644
============================================================

Test dataset summary statistics:
---------------------------------------------
                 id                 date     store_nbr   onpromotion
count  2.851200e+04                28512  28512.000000  28512.000000
mean   3.015144e+06  2017-08-23 12:00:00     27.500000      6.965383
min    3.000888e+06  2017-08-16 00:00:00      1.000000      0.000000
25%    3.008016e+06  2017-08-19 18:00:00     14.000000      0.000000
50%    3.015144e+06  2017-08-23 12:00:00     27.500000      0.000000
75%    3.022271e+06  2017-08-27 06:00:00     41.000000      6.000000
max    3.029399e+06  2017-08-31 00:00:00     54.000000    646.000000
std    8.230850e+03                  NaN     15.586057     20.683952
============================================================

Train dataset summary statistics:
---------------------------------------------
                 id                           date     store_nbr  \
count  3.000888e+06                        3000888  3.000888e+06   
mean   1.500444e+06  2015-04-24 08:27:04.703088384  2.750000e+01   
min    0.000000e+00            2013-01-01 00:00:00  1.000000e+00   
25%    7.502218e+05            2014-02-26 18:00:00  1.400000e+01   
50%    1.500444e+06            2015-04-24 12:00:00  2.750000e+01   
75%    2.250665e+06            2016-06-19 06:00:00  4.100000e+01   
max    3.000887e+06            2017-08-15 00:00:00  5.400000e+01   
std    8.662819e+05                            NaN  1.558579e+01   

              sales   onpromotion  
count  3.000888e+06  3.000888e+06  
mean   3.577757e+02  2.602770e+00  
min    0.000000e+00  0.000000e+00  
25%    0.000000e+00  0.000000e+00  
50%    1.100000e+01  0.000000e+00  
75%    1.958473e+02  0.000000e+00  
max    1.247170e+05  7.410000e+02  
std    1.101998e+03  1.221888e+01  

##### Check for missing values in all the datasets

Missing values in Holidays Dataset:
date           0
type           0
locale         0
locale_name    0
description    0
transferred    0
dtype: int64

Missing values in Oil Dataset:
date           0
dcoilwtico    43
dtype: int64

Missing values in Stores Dataset:
store_nbr    0
city         0
state        0
type         0
cluster      0
dtype: int64

Missing values in Transactions Dataset:
date            0
store_nbr       0
transactions    0
dtype: int64

Missing values in Test Dataset:
id             0
date           0
store_nbr      0
family         0
onpromotion    0
dtype: int64

Missing values in Train Dataset:
id             0
date           0
store_nbr      0
family         0
sales          0
onpromotion    0
dtype: int64

It is only the 'dcoilwtico' column found in the Oil dataset that has 43 missing values.

#### Handling the Missing Values in the 'dcoilwtico' (daily crude oil prices) column of the Oil Dataset.

#### Visualizing the 'dcoilwtico' column to Identify a Strategy for Handling Missing Values

![image](https://github.com/NginaMuinde/LP3-Regression-Project/assets/149095447/28a7dc46-fda1-47e3-a481-0d2c212ac980)
 
Fill missing values in the 'dcoilwtico' column using backfill strategy
Visualize the 'dcoilwtico' column to confirm proper handling of Missing Values

![image](https://github.com/NginaMuinde/LP3-Regression-Project/assets/149095447/360d8a3b-db97-4546-af10-a3d938fcd23b)

Missing values in the 'dcoilwtico' column have been well handled.

#### Create visualizations illustrating the frequency of data collection points on a yearly and monthly basis.
![image](https://github.com/NginaMuinde/LP3-Regression-Project/assets/149095447/0417327b-d99e-4568-889b-b4d73e92c57f)

From 2013 to 2016, the data counts remained consistent, but there was a decline in 2017.

#### Count of Number of Data Points Each Month

![image](https://github.com/NginaMuinde/LP3-Regression-Project/assets/149095447/e524ec0b-6f13-44d4-b6b7-0b9a44846cbc)

The distribution of data points appears to be relatively consistent across the months.

 ## Check for the completeness of the 'date' column in the Train Dataset

 Check the completeness of the train dataset

 The train dataset is incomplete. The following dates are missing:
DatetimeIndex(['2013-12-25', '2014-12-25', '2015-12-25', '2016-12-25'], dtype='datetime64[ns]',

Complete the missing dates in the train dataset
Create an index of the missing dates as a DatetimeIndex object

#### Is the train dataset complete (has all the required dates)?

![image](https://github.com/NginaMuinde/LP3-Regression-Project/assets/149095447/d25cf039-3017-4555-a4d1-aa106d9b5f43)

Missing dates have been handled successfully

### Merging The Train Dataset with the Stores, Transactions, Holiday Events and Oil Dataset

![image](https://github.com/NginaMuinde/LP3-Regression-Project/assets/149095447/3d07dfe8-7795-4432-b270-d2b9b787470c)


In the Favorita corporation's time series forecasting project, employing an inner merge proves beneficial for maintaining data consistency, preventing missing values, and concentrating on pertinent data for precise predictions.

An inner merge selectively retains rows with matching values in specified columns. In the context of time series forecasting, it allows the merging of datasets based on a common time index or timestamp. This ensures that only rows with corresponding timestamps in both datasets are included, aligning different data sources accurately for building a reliable forecasting model.

The use of an inner merge is crucial in time series forecasting as it eliminates non-matching timestamps, ensuring alignment and consistency in the data. Focusing on the intersection of datasets enables the creation of a merged dataset containing essential information for accurate time series forecasting.

##### Check the column information of the merged dataset

![image](https://github.com/NginaMuinde/LP3-Regression-Project/assets/149095447/385f95db-dc1a-4bc6-886a-0e30a82f7a39)

The merged dataset after merging the train dataset with additional datasets contains 322,047 rows and 16 columns.
Two columns have been renamed as a result of the merging, type_x and type_y.

![image](https://github.com/NginaMuinde/LP3-Regression-Project/assets/149095447/b3a7db56-484d-4020-bb6a-d3921ef1843e)

- The type_x column represents the store type.
- The type_y column represents the holiday type.

I renamed the columns with the approapriate names

![image](https://github.com/NginaMuinde/LP3-Regression-Project/assets/149095447/83381eb8-76d3-4e37-9aca-4ff4cb77cebe)

 Generated summary statistics and checked for missed values

 ![image](https://github.com/NginaMuinde/LP3-Regression-Project/assets/149095447/45b62a74-9e4c-4542-8e1c-57f16e6812f2)

The merged dataset has no missing values.

There were no duplicates in the merged and test datasets

## Univariate, Bivariate  and Multivariate Analysis

#### a.    Distribution of Types of Holidays
#### a(i). Distribution of Transferred Holidays

![image](https://github.com/NginaMuinde/LP3-Regression-Project/assets/149095447/b108e7b9-52ff-411b-ba89-dc02258a2028)

#### b. Trend of the Sales variable:

![image](https://github.com/NginaMuinde/LP3-Regression-Project/assets/149095447/bfe6124a-9165-4982-8b59-b91843a20e15)

The above graph offers a glimpse into the daily unit sales distribution. It reveals a peak that signifies a consistent upward trend from year to year.

#### c. Trend of the transactions variable

![image](https://github.com/NginaMuinde/LP3-Regression-Project/assets/149095447/360c689e-70b0-4850-ae3a-b645cb5a6ba3)

The above graph offers valuable insights into the transaction distribution within the dataset. The shape of the longest spikes reveal that around 23rd to 24th December every year a significant proportion of transactions are made indicating seasonality. 

#### d. Distribution of the 'Daily Oil Price' variable:

![image](https://github.com/NginaMuinde/LP3-Regression-Project/assets/149095447/d332501f-3f72-4ffa-8840-73bcb6c28e60)

The 'dcoilwtico' variable is examined through a histogram to gain understanding into its distribution. The histogram visually shows the frequency of the distribution of oil prices, illustrating the occurrences for specific price ranges.

#### e. Distribution of Store Types
![image](https://github.com/NginaMuinde/LP3-Regression-Project/assets/149095447/4c67f24b-c2bc-4587-b75e-9fe36eb90122)

#### f. Distribution of Clusters in Stores Dataset

![image](https://github.com/NginaMuinde/LP3-Regression-Project/assets/149095447/fd010033-3d6a-4c69-8ac2-c93260f73867)

### ii. Bivariate Analysis

#### a. Trend of sales during holidays.

![image](https://github.com/NginaMuinde/LP3-Regression-Project/assets/149095447/577fcce2-e5fe-4cf7-9300-2ccb76da7b86)

The figure above shows the trend of sales during specific holiday types. From the graph, we can observe that the sales exhibit some variations and fluctuations depending on holiday type showing periods of both high and low sales. This indicates seasonality; each holiday affects sales patterns uniquely.

#### b. Average Sales Performance of Stores by Cluster

![image](https://github.com/NginaMuinde/LP3-Regression-Project/assets/149095447/9f0d1926-e408-4d0d-b7ca-28acacc341fb)

The cluster with the highest number of stores is Cluster 5, followed by Clusters 14, 8, 11 and 12. These clusters have a significantly larger number of stores compared to the others.

#### c. Sales performance on the various product family types  

![image](https://github.com/NginaMuinde/LP3-Regression-Project/assets/149095447/0da85597-7a09-4c4e-b62a-5599b7f3d86b)

The graph illustrates the sales performance of the top 10 product families. Grocery I and beverages exhibit the highest sales, indicating their popularity among customers. Produce and cleaning products also demonstrate significant sales, reflecting the importance of fresh produce and household cleaning supplies. Dairy, bread/bakery, poultry, and meats contribute to overall sales, suggesting the demand for essential food items. Personal care and deli products have relatively lower sales but still play a role in the product mix.

#### d. Variation of sales across different store numbers

![image](https://github.com/NginaMuinde/LP3-Regression-Project/assets/149095447/79c84ed1-38fc-416b-b512-20e0748235b4)

Various store identifiers demonstrate distinct sales patterns, with certain store numbers reflecting elevated sales figures and others displaying comparatively lower sales.
Stores number 3,44,45,46,47,48,49, 51 have the highest volume of sales.

#### e. Trend of Daily Crude oil Prices ('dcoilwtico') Over Time

![image](https://github.com/NginaMuinde/LP3-Regression-Project/assets/149095447/01d3c014-4e6f-4d9a-a8e5-8eeb55e4bb6a)

#### e(i). Trend of oil prices in relation to sales Over Time

![image](https://github.com/NginaMuinde/LP3-Regression-Project/assets/149095447/ad92ec91-df5c-4658-867e-b58fd297d99d)

It is noticeable that the drop in oil prices does not appear to influence sales, as demonstrated by the lack of a clear relationship between oil price reductions and sales in the plot. Consequently, we conclude that the oil price data is not significant for our modeling purposes and therefore will be excluded.

#### f. Total Count of Sales by Store Type

![image](https://github.com/NginaMuinde/LP3-Regression-Project/assets/149095447/676fa158-6c4e-415a-9748-82d3d253763f)

The total sales differ among various store types, with Store Type D leading, making a substantial contribution to the overall revenue. Following closely is Store Type A demonstrating significant sales performance. Store Type C holds the third position in total sales, while Store Type B and Store Type E have comparatively lower sales amounts. 

Analyzing sales variations by store type enables the identification of key revenue drivers and underscores the significance of specific store types in influencing overall sales.

##### g. Top 5 Sales Categories Per Year

![image](https://github.com/NginaMuinde/LP3-Regression-Project/assets/149095447/acbb0346-121d-4f57-926b-4e82169d2b8d)

#### h. Average Sales by City

![image](https://github.com/NginaMuinde/LP3-Regression-Project/assets/149095447/3afa2787-d943-4fb1-a410-7cceaab7094c)

Quito stands out with the largest average sales count, significantly surpassing all other cities. Cayambe ranks second in terms of average sales, followed by Ambato, Daule, and Loja. Some cities exhibit a moderate average sales count, while others have less. Puyo and Playas in particular, record the lowest average sales numbers.

#### i. Average Sales by State

![image](https://github.com/NginaMuinde/LP3-Regression-Project/assets/149095447/243bb562-c8a3-4f43-b49f-07d3460bc17f)

Pichincha leads in store count and consequently in average sales. This may be due to the fact that Quito is its capital. Guayas ranks second, driven by the presence of Guayaquil. States like Santo Domingo de los Tsachilas, Azuay, Manabi, Cotopaxi, Tungurahua, Los Rios, El Oro, Chimborazo, Imbabura, Bolivar, Pastaza, Santa Elena, and Loja maintain a moderate store count.

#### j. Relationship between sales and transactions

![image](https://github.com/NginaMuinde/LP3-Regression-Project/assets/149095447/5dfb8abd-c34c-48d1-a417-d0703dfada82)

The scatter plot illustrates the correlation between sales and transactions in the dataset, with each data point representing a specific instance and its corresponding sales and transaction values. Key observations from the scatter plot include:

Clustered Data Points: The majority of data points concentrate in the lower sales region, implying consistent associations between specific transaction volumes and sales levels. This clustering suggests the existence of recurring sales patterns or trends at certain transaction levels.

Outliers: Some data points deviate from the main cluster, indicating instances with notably higher sales for relatively lower transaction volumes or vice versa. These outliers signify exceptional cases that diverge from typical observations, offering insights into uncommon sales scenarios or extraordinary business activities.

In conclusion, the scatter plot yields valuable insights into the interplay of sales and transactions. The clustered data points reveal common patterns, while outliers highlight unique instances that merit further exploration. This analysis equips businesses with valuable information to make informed decisions and formulate effective strategies for enhancing sales performance.

### iii. Multivariate Analysis

#### a. Correlation matrix of numerical variables
![image](https://github.com/NginaMuinde/LP3-Regression-Project/assets/149095447/dd86d28e-22ae-483b-ae15-381a89bb10d6)


Correlation values, ranging from -1 to 1, provide insights into the relationships between variables. A perfect negative correlation is represented by -1, a perfect positive correlation by 1, and no correlation by 0. The correlation matrix below highlights associations between different variables:

- Sales and Transactions:

A weak positive correlation of approximately 0.200 exists between "Sales" and "Transactions." This implies a slight positive relationship, suggesting that as the number of transactions increases, there is a tendency for sales to rise. However, the correlation is not notably strong.

- Sales and Dcoilwito (Daily Crude Oil Prices):

A weak negative correlation of approximately -0.062 is observed between "Sales" and "Dcoilwito" (Oil Prices). This signifies a slight negative relationship, indicating that as oil prices increase, there is a tendency for sales to decrease slightly. However, the correlation is not considered significant.

- Transactions and Dcoilwito (Oil Prices):

A very weak negative correlation of approximately -0.017 is noted between "Transactions" and "Dcoilwito" (Oil Prices). This implies an almost negligible relationship, suggesting that fluctuations in oil prices have minimal impact on the number of transactions.

In summary, the correlation values are relatively low, indicating that the relationships between these variables are not very robust. Other unexplored factors may influence sales, transactions, and oil prices. It is crucial to delve into additional variables to obtain a more comprehensive understanding of their collective impact on sales and transactions.

#### b. Scatter Plot Marrix of numerical Variables
![image](https://github.com/NginaMuinde/LP3-Regression-Project/assets/149095447/f52f2d13-45d9-4efe-bad8-cc7d26b1af9e)


The findings from the scatter plot matrix align with those derived from the correlation matrix.

#### Additional Visuals

![image](https://github.com/NginaMuinde/LP3-Regression-Project/assets/149095447/0a90dedd-e1fb-43fc-8549-c4642e9f124f)

![Uploading image.png…]()


## Stationarity Test
Stationarity refers to the constancy of statistical characteristics, such as mean and variance, in a time series over time. In this context, the Augmented Dickey-Fuller (ADF) test was employed on the 'sales' data within the 'merged_df' dataset to assess stationarity. The ADF test is a standard method for examining stationarity in time series data.
- Null hypothesis (H0): The sales data is non-stationary.
- Alternative hypothesis (H1): The sales data is stationary. 


Null Hypothesis (H0): The sales data is non-stationary.

This hypothesis assumes that the statistical properties of the sales data, such as mean and variance, do not remain constant over time. Essentially, it posits that there is a presence of trends or patterns in the data that make it non-stationary.

Alternative Hypothesis (H1): The sales data is stationary.
Conversely, the alternative hypothesis suggests that the sales data is stationary, meaning that its statistical properties remain constant over time. If the alternative hypothesis is supported, it implies that the sales data does not exhibit significant trends or patterns.


The objective of this hypothesis testing is to determine whether stationarity exists in the sales data, which is crucial in time series analysis. Stationary time series data simplifies forecasting and modeling as it allows for more reliable predictions based on historical patterns. The rejection or acceptance of the null hypothesis provides insights into the nature of the underlying sales data.








