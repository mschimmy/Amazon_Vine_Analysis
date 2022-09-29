# Amazon Vine Analysis

## Overview of the Analysis
The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. Companies like the client, SellBy, pay a small fee to Amazon and provide products to Amazon Vine members, who are then required to publish a review. The reviews are stored in an online database hosted by Amazon Web Services and can be accessed using this [link](https://s3.amazonaws.com/amazon-reviews-pds/tsv/index.txt).

### Purpose
The purpose of this analysis is to perform the ETL process to extract the dataset, transform the dataset, connect it to an AWS RDS instance, and load the transformed data into pgAdmin. Then PySpark will be used to determine if there is any bias toward favorable reviews from Vine members in the dataset. The dataset used in this analysis contains review information for watches and can be downloaded using this [link](https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Watches_v1_00.tsv.gz
).

## Results
![Vine Reviews](https://github.com/mschimmy/Amazon_Vine_Analysis/blob/main/images/Vine_reviews.png)
<sub>Vine Reviews</sub>

![Non-Vine Reviews](https://github.com/mschimmy/Amazon_Vine_Analysis/blob/main/images/Non-Vine_reviews.png)
<sub>Non-Vine Reviews</sub>

![Review Counts and Percentages](https://github.com/mschimmy/Amazon_Vine_Analysis/blob/main/images/Review_counts_percentages.png)
<sub>Review Counts and Percentages</sub>

### Analysis
How many Vine reviews and non-Vine reviews were there?
- There were a total of 47 Vine reviews and 8,362 non-Vine reviews in the dataset.

How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?
- There were a total of 15 5-star Vine reviews and 4,332 5-star non-Vine reviews in the dataset.

What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?
- The percentage of 5-star Vine reviews was 31.915%, and the percentage of 5-star non-Vine reviews was 51.806%.

## Summary
The purpose of this analysis is to determine if there is any bias towards reviews that were written as part of the Vine program and if having a paid Vine review makes a difference in the percentage of 5-star reviews.

After conducting the ETL process and conducting the analysis, it was determined that there is not any bias towards Vine reviews rating the product as having 5 stars when compared to non-Vine 5-star reviews.

An additional analysis that could be performed on the dataset to confirm this statement would be to conduct a Mann-Whitney U Test to determine whether the means of Vine star ratings and non-Vine star ratings are statistically different.
