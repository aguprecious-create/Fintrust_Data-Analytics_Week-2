# Fintrust_Data-Analytics_Week-2
Project Overview
The FinTrust Financial Intelligence & Digital Banking Support Solution is a multidisciplinary project focused on using data and digital tools to understand customer behaviour, transaction activity, data quality, and potential areas for operational improvement within a synthetic digital banking environment.
During Week 2, the Data Analytics track focused on practical data preparation, validation, exploratory analysis, SQL-based business analysis, and dashboard development. The analysis used FinTrust's customer and transaction datasets covering January to March 2026.
The objective was to transform the raw datasets into validated information and business insights that can support understanding of transaction patterns, customer segments, digital channels, transaction performance, and areas requiring further review.
Data Sources
	Dataset	Records	Purpose
1	FinTrust Customer Data	1,500	Customer demographics, account information and digital engagement
2	FinTrust Transaction Data	12,000	Transaction activity, amounts, channels, status and synthetic review labels
3	FinTrust Data Dictionary	N/A	Definitions and descriptions of dataset fields
The datasets were provided as synthetic educational data for the FinTrust project. Customer ID was used as the common key for joining customer and transaction information.
Data Quality and Cleaning
Data-quality checks were performed before the main analysis. These checks covered record counts, duplicate identifiers, missing values, data types, date ranges and customer-transaction join integrity.
S/N	Check	Result
1	Customer records	1,500
2	Transaction records	12,000
3	Duplicate Customer IDs	0
4	Duplicate Transaction IDs	0
5	Missing Device Type	96
6	Missing Location	96
7	Unmatched transaction Customer IDs	0
8	Transaction period	Jan 1 – Mar 31, 2026
The 96 missing Device Type values and 96 missing Location values were retained rather than removed because they form part of the provided dataset and were relevant to the data-quality assessment. The missing values should be considered when interpreting analyses involving these fields.
SQL Analysis
SQLite- Visual Studio Code was used to perform structured querying and validation of the FinTrust datasets. SQL analysis was used to calculate transaction totals, transaction-type performance, monthly activity, transaction status, channel activity, customer-segment activity, risk-review labels, location activity and international transaction patterns.

S/N	Metric	Result
1	Total transactions	12,000
2	Total transaction value	₦560,477,354.85
3	Average transaction value	₦46,706.45
4	Successful transactions	10,856
5	Failed transactions	630
6	Reversed transactions	326
7	Pending transactions	188
8	Risk Review Flag = Yes	2,352 (19.6%)
9	International transactions	480 (4.0%)
The SQL validation checks indicate that the customer and transaction data were successfully loaded into SQLite and are structurally consistent for analysis. No duplicate customer or transaction identifiers were found, all transaction records matched a customer record, and transaction totals reconciled with the source data. The identified missing Device_Type and Location values were also confirmed.

Python Exploratory Data Analysis
Jupyter Lab was used for exploratory data analysis using pandas and Matplotlib. The analysis examined customer characteristics, transaction distributions, monthly trends, transaction values, customer segments, channels, transaction types, international transactions and synthetic risk-review labels.
Key Python observations
The average customer age is approximately 41.6 years. 
Average customer tenure is approximately 49.9 months. 
Average digital engagement score is approximately 68.0. 
Mobile App is the most common transaction channel. 
Transfer is the largest transaction type by transaction volume and total value. 
March recorded the highest monthly transaction value at approximately ₦196.2 million. 
Everyday customers generated the highest transaction volume and total transaction value. 
SME customers had the highest average transaction value at approximately ₦49,116. 
Transactions labelled Risk_Review_Flag = Yes had a higher average transaction value than transactions labelled No. 

Power BI Dashboard
A Power BI dashboard was developed to provide an interactive summary of FinTrust transaction performance and customer activity.
Dashboard KPIs:
Total Customers: 1.5K
Total Transaction Value: ₦560.48M 
Total Transactions: 12K 
Average Transaction Value: ₦46.71K 
Transaction Success Rate: 90.47% 
Dashboard visuals include:
Monthly Transaction Value 
Transaction Value by Channel 
Transaction Value by Customer Segment 
Average Transaction Value by Customer Segment 
Transaction Volume by Type 
Transaction Value by Location 
Transaction Status Distribution 
Risk Review Flag Distribution 

Key Business Findings 
1.Mobile App is the dominant transaction channel
Finding: Mobile App is the most heavily used transaction channel.
Evidence: It recorded 5,102 transactions with a total transaction value of approximately ₦240.1 million, the highest among the channels.
Business Meaning:
The Mobile App represents a major part of FinTrust’s digital transaction activity. Its performance and customer experience are therefore important areas for operational monitoring.
2.Everyday customers generate the highest transaction activity
Finding: Everyday customers account for the largest share of transaction activity among customer segments.
Evidence: Everyday customers generated 5,644 transactions worth approximately ₦261.5 million.
Business Meaning:
The Everyday segment represents a substantial portion of FinTrust’s transaction activity. Understanding and retaining this customer group could therefore be important for maintaining transaction volume.
3.SME customers have the highest average transaction value
Finding: SME customers have the highest average transaction value despite having the lowest transaction volume among the four customer segments.
Evidence: SME customers recorded an average transaction value of approximately ₦49,116, compared with approximately ₦46,325 for Everyday, ₦45,638 for Premium and ₦46,953 for Student customers.
Business Meaning:
Although SMEs generate fewer transactions, their individual transactions tend to involve higher values. This may make the SME segment relevant when examining higher-value transaction activity.
4.Ibadan records the highest transaction value and average transaction size
Finding: Ibadan has the highest transaction value and average transaction size among the transaction locations in the dataset.
Evidence: Ibadan recorded 1,550 transactions, worth approximately ₦81.4 million, with an average transaction value of approximately ₦52,526.
Business Meaning:
Transaction activity varies across locations. This provides an opportunity for FinTrust to investigate whether differences in customer behaviour, transaction mix or channel usage could explain the higher transaction values observed in Ibadan.
5.Risk-review-labelled transactions have higher average values
Finding: Transactions labelled for risk review have a substantially higher average transaction value than transactions not labelled for review.
Evidence: The 2,352 risk-review-labelled transactions (19.6%) had an average value of approximately ₦68,786, compared with approximately ₦41,324 for the 9,648 transactions not labelled for review.
Business Meaning:
Within this synthetic dataset, the risk-review label is associated with higher-value transactions. This pattern may be useful for further investigation by the relevant risk/data-science teams.

6.Risk-review-labelled transactions have higher average values
Finding: Transactions labelled for risk review have a substantially higher average transaction value than transactions not labelled for review.
Evidence: The 2,352 risk-review-labelled transactions (19.6%) had an average value of approximately ₦68,786, compared with approximately ₦41,324 for the 9,648 transactions not labelled for review.
Business Meaning:
Within this synthetic dataset, the risk-review label is associated with higher-value transactions. This pattern may be useful for further investigation by the relevant risk/data-science teams.
7.Transfers have the highest review-label rate
Finding: Transfer transactions have the highest proportion of risk-review labels among transaction types.
Evidence: Approximately 28.5% of transfers were labelled for review, followed by cash withdrawals at 25.3%. Bill payments had the lowest rate at approximately 12.8%.
Business Meaning:
Transaction type appears to be associated with different levels of risk-review activity in the synthetic dataset. Transfers and cash withdrawals could therefore be areas for further investigation when examining transaction-review patterns.