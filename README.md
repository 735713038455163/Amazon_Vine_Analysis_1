# Amazon_Vine_Analysis_1
Using Google Colab PySpark to perform the ETL process to extract the dataset, transform the data, connect to an AWS RDS instance, and load the transformed data into pgAdmin. Next, use PySpark, Pandas, or SQL to determine if there is any bias toward favorable reviews from Vine members in the dataset.Analyzing Amazon reviews written by members of the paid Amazon Vine program. The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. Companies like SellBy pay a small fee to Amazon and provide products to Amazon Vine members, who are then required to publish a review.


# Overview of analysis

Here is the list of deliverables:

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

- Where the percentage of helpful_votes is equal to or greater than 50%. Companies like SellBy pay a small fee to Amazon and provide products to Amazon Vine members, who are then required to publish a review. On the data already filtered by total_votes where we will review the remaining 3,699,249 votes and count of 70,474 unique_id's reviewers who have also submited more than 20 reviews. The percentage of helpful_votes means that we have to review the cooresponding date to the current filtered data in filtered_vine_table data. If also filtered by only reviewing where 50% were helpful. We then have a count of 63294 helpful results.
![D2.Q2b](https://github.com/735713038455163/Amazon_Vine_Analysis_1/blob/master/D2-%20Tables%20%26%20Code/D2.Q2b.PNG) 

- Where there is a Vine review. For paid Vines selected as "Yes" the count is reduced to on 1266 paid vine reviews, over 50% helpful and have more than 20 reviews. 
![D2.Q2c](https://github.com/735713038455163/Amazon_Vine_Analysis_1/blob/master/D2-%20Tables%20%26%20Code/D2.Q2c.PNG)

- Where there isn’t a Vine review. For paid Vines selected as "NO" the count is reduced to on 62,028 unpaid vine reviews, over 50% helpful and have more than 20 reviews.
![D2.Q2d](https://github.com/735713038455163/Amazon_Vine_Analysis_1/blob/master/D2-%20Tables%20%26%20Code/D2.Q2d.PNG)

-The total number of reviews, the number of 5-star reviews, and the percentage 5-star reviews are calculated for all Vine and non-Vine reviews of the filtered data over 50% helpful and have more than 20 reviews suggest the following:

On filtered data
- 1266 paid Vine reviews and 62,028 unpaid non-Vine reviews on filtered data.
![D3aPNG](https://github.com/735713038455163/Amazon_Vine_Analysis_1/blob/master/D2-%20Tables%20%26%20Code/D3aPNG.PNG)
- 434 paid Vine reviews were 5 stars, 29,982 were 5 star unpaid non-Vine reviews on filtered data. 
![D3b](https://github.com/735713038455163/Amazon_Vine_Analysis_1/blob/master/D2-%20Tables%20%26%20Code/D3b.PNG)
- Lastly, 34.28% (424/1266) percentage of paid Vine reviews were 5 stars, and 48% (29,982/62,028) of non-Vine reviews were 5 stars.

# Summary 

- Considering the original data set when the original total sum of total votes is 9,089,473 with a count of 4,864,243 of individual reviewers who have a single review ID who have submitted a total of 9,089,473 reviews.
![D2.Count%20vine_table.](https://github.com/735713038455163/Amazon_Vine_Analysis_1/blob/master/D2-%20Tables%20%26%20Code/D2.Count%20vine_table..PNG)
![D2.SUM%20vine_table.](https://github.com/735713038455163/Amazon_Vine_Analysis_1/blob/master/D2-%20Tables%20%26%20Code/D2.SUM%20vine_table..PNG)

On non filtered data
-  41,835 paid Vine reviews and 4,822,408 non-paid reviews, a 6 null. 
![D3a-og](https://github.com/735713038455163/Amazon_Vine_Analysis_1/blob/master/D2-%20Tables%20%26%20Code/D3a-og.PNG)
- 17,071 paid Vine reviews were 5 stars, 3,059,846 were 5 star unpaid non-Vine reviews on filtered data. 
![D3c](https://github.com/735713038455163/Amazon_Vine_Analysis_1/blob/master/D2-%20Tables%20%26%20Code/D3c.PNG)

- Lastly, 40.8% (17,071/41,835) percentage of paid Vine reviews were 5 stars, and 63.45% (3059846/4822408) of non-Vine reviews were 5 stars.

Perhaps looking at filtered data compared to the un-filtered vine data both support the same conclusion. There is no bias from the sample filtered set, and the larget set. The data filtered we only looked at 40.69% of reviews, and 1.44% of the review ID counts, which it indicated that there is alot more people submitted less than 20 reviews. Yet they both support the conclusion that there are more 5star unpaid reviews on toys data that are helpful whereby the reviewer are either unpaid or paid, and that depsit being paid there are still more unpaid 5 star reviews that are helpful and at zero cost then paid 5star review. This leads can lead to deciding whether or not its worth the paid reviews or if open source reviews are more successful. 



