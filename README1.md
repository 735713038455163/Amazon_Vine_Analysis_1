# Amazon_Vine_Analysis_1
Using Google Colab PySpark to perform the ETL process to extract the dataset, transform the data, connect to an AWS RDS instance, and load the transformed data into pgAdmin. Next, use PySpark, Pandas, or SQL to determine if there is any bias toward favorable reviews from Vine members in the dataset.Analyzing Amazon reviews written by members of the paid Amazon Vine program. The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. Companies like SellBy pay a small fee to Amazon and provide products to Amazon Vine members, who are then required to publish a review.


# Overview of Project

During the 16th week of the Trilogy University of Toronto Data Analytics & Visualization Bootcamp our Module 16 challenge is to create a written analysis with 3 key deliverables as follows; 

Here is the list of deliverables for the analysis of 3 deliverables:

#### Deliverable 1: Perform ETL on Amazon Product Reviews
#### Deliverable 2: Determine Bias of Vine Reviews
#### Deliverable 3: A Written Report on the Analysis (README.md)


Specifically,

The files we will be using are :SQL table schema.sql, Amazon_Reviews_ETL.ipynb, with the followng data set: 

https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Toys_v1_00.tsv.gz


# Purpose

1) The Amazon_Reviews_ETL.ipynb file reviews the dataset and is extracted as a DataFrame. The extracted dataset is transformed into four DataFrames with the correct columns.
All four DataFrames are loaded into their respective tables in pgAdmin.

1- customer_table ![D1.customer_table](https://github.com/735713038455163/Amazon_Vine_Analysis_1/blob/master/D1-%20Tables%20%26%20Code/D1.customer_table.PNG)
2- products_table ![D1.Product_Table](https://github.com/735713038455163/Amazon_Vine_Analysis_1/blob/master/D1-%20Tables%20%26%20Code/D1.Product_Table.PNG)
3- review_id_table ![D1.review_id_table](https://github.com/735713038455163/Amazon_Vine_Analysis_1/blob/master/D1-%20Tables%20%26%20Code/D1.review_id_table.PNG)
4- vine_table ![D1.vine_table](https://github.com/735713038455163/Amazon_Vine_Analysis_1/blob/master/D1-%20Tables%20%26%20Code/D1.vine_table.PNG)

2) Using SQL to determine if there is any bias towards reviews that were written as part of the Vine program to see if having a paid Vine review makes a difference in the percentage of 5-star reviews.

There is a DataFrame or table for the vine_table data using SQL

- In the vine_table there are 6 coulumns; review_id, star_rating, helpful_votes, total_votes, vine, verified_purchase. 

- Whereby the sum of total votes, will change as well as the count of total votes because we are going to filter to count total of reviews that produces over 20 reviews. When we filter, to see only 20 or more total votes, the sum is 3,699,249 votes and count is 70,474.
![D2.Countoffilteredreviews](https://github.com/735713038455163/Amazon_Vine_Analysis_1/blob/master/D2-%20Tables%20%26%20Code/D2.Countoffilteredreviews..PNG)
![D2.Sumoffilteredreviews](https://github.com/735713038455163/Amazon_Vine_Analysis_1/blob/master/D2-%20Tables%20%26%20Code/D2.Sumoffilteredreviews..PNG)
![D2.Q2a](https://github.com/735713038455163/Amazon_Vine_Analysis_1/blob/master/D2-%20Tables%20%26%20Code/D2.Q2a.PNG)

<<<<<<< HEAD
- Where the percentage of helpful_votes is equal to or greater than 50%. Companies like SellBy pay a small fee to Amazon and provide products to Amazon Vine members, who are then required to publish a review. On the data already filtered by total_votes where we will review the remaining 3,699,249 votes and count of 70,474 unique_id's reviewers who have also submited more than 20 reviews. The percentage of helpful_votes means that we have to review the cooresponding date to the current filtered data in filtered_vine_table data. If also filtered by only reviewing where 50% were helpful. We then have a count of 63,294 helpful results from unique review_id.![D2.Q2b](https://github.com/735713038455163/Amazon_Vine_Analysis_1/blob/master/D2-%20Tables%20%26%20Code/D2.Q2b.PNG) 
- where there is a Vine review 
=======
- Where the percentage of helpful_votes is equal to or greater than 50%. Companies like SellBy pay a small fee to Amazon and provide products to Amazon Vine members, who are then required to publish a review. On the data already filtered by total_votes where we will review the remaining 3,699,249 votes and count of 70,474 unique_id's reviewers who have also submited more than 20 reviews. The percentage of helpful_votes means that we have to review the cooresponding date to the current filtered data in filtered_vine_table data. If also filtered by only reviewing where 50% were helpful. We then have a count of 63294 helpful results.![D2.Q2b](https://github.com/735713038455163/Amazon_Vine_Analysis_1/blob/master/D2-%20Tables%20%26%20Code/D2.Q2b.PNG) 
- Where there is a Vine review. For paid Vines selected as "Yes" the count is reduced to on 1266 paid vine reviews, over 50% helpful and have more than 20 reviews. 
![D2.Q2b](https://github.com/735713038455163/Amazon_Vine_Analysis_1/blob/master/D2-%20Tables%20%26%20Code/D2.Q2b.PNG)



>>>>>>> 5fd4f6b35a3cadfcad336888a56877300c783611
- where there isn’t a Vine review 

The total number of reviews, the number of 5-star reviews, and the percentage 5-star reviews are calculated for all Vine and non-Vine reviews (15 pt)

# Data Analytics 

The original total sum of total votes is 9,089,473 with a count of 4,864,243 of individual reviewers who have a single review ID who have submitted a total of 9,089,473 reviews.
![D2.Count%20vine_table.](https://github.com/735713038455163/Amazon_Vine_Analysis_1/blob/master/D2-%20Tables%20%26%20Code/D2.Count%20vine_table..PNG)
![D2.SUM%20vine_table.](https://github.com/735713038455163/Amazon_Vine_Analysis_1/blob/master/D2-%20Tables%20%26%20Code/D2.SUM%20vine_table..PNG)

#### Analysis and Challenges
#### Analysis of Outcomes
#### Challenges and Difficulties Encountered


# Results & Visualization 
#### What are two conclusions you can draw about the Outcomes

We retrived the 40.69% of reviews, and 1.44% of the review ID counts, which it indicated that there is alot more people submitted less than 20 reviews.

#### What can you conclude about the Outcomes
#### What are some limitations of this dataset?

We cannot looking at time frame ther are no timestamp data.  

#### What are some other possible

