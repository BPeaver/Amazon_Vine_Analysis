# Amazon_Vine_Analysis

## Overview
In a world of online consumerism, reviews have become one of the greatest methods for a product to get the attention of a potential buyer. Coveted 5-star reviews and maligned 1-star reviews help consumers make decisions based on, theoretically, the experiences of someone who has already used the product. Amazon is one of many online shopping websites, if not THE online shopping site, with thousands of potential products ranging from groceries to clothes to electronics and beyond. The myriad products on offer through Amazon have reviews tied to them, sometimes numbering in the thousands. 

How does a consumer make an informed decision when there are so many reviews tied to any one item? Amazon's Vine program allows customers who have a history of making informed, thoughtful product reviews, to be showcased and even recieve early access to products to help generate reviews. This allows shoppers to see reviews on even brand new items, provided by companies like SellBy. 

Do these Vine reviews have bias? Are they more likely to give out coveted 5-star reviews to products provided by companies like SellBy? 



## Analysis
Using the Amazon Reviews dataset for toys (https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Toys_v1_00.tsv.gz), we were able to extract, transform, and load the review data and break it down into Vine and Non-Vine reviews. 

### Databases
We established databases using PGadmin and Amazon AWS to hold the data as we transformed and manipulated it into more useful data for us

![database erd](https://github.com/BPeaver/Amazon_Vine_Analysis/blob/main/Images/database%20erd.png)

![customer table](https://github.com/BPeaver/Amazon_Vine_Analysis/blob/main/Images/customer%20table.png)

![review id  table](https://github.com/BPeaver/Amazon_Vine_Analysis/blob/main/Images/review%20id%20table.png)

![product table](https://github.com/BPeaver/Amazon_Vine_Analysis/blob/main/Images/product%20table.png)

![vine table](https://github.com/BPeaver/Amazon_Vine_Analysis/blob/main/Images/vine%20table.png)

### Breakdown

1: The number of reviews for this data set were fairly large, totalling more than 63,000 combined

![total votes](https://github.com/BPeaver/Amazon_Vine_Analysis/blob/main/Images/total%20votes.png)

2: Breaking this total down into 5-star reviews was essential to see if Vine reviewers were showing any sort of bias

![total 5 start](https://github.com/BPeaver/Amazon_Vine_Analysis/blob/main/Images/total%205%20star.png)

3: The actual percentage of 5-star reviews does appear to be lower for Vine reviewers than Non-Vine reviews
![percent 5 star](https://github.com/BPeaver/Amazon_Vine_Analysis/blob/main/Images/percent%205%20star.png)

## Summary
At first glance, it would appear that Vine reviews have no real bias toward giving out 5-star reviews for products. With them posting a lower 5-star review rate than Non-Vine reviewers by 14%. However, more analysis could be done to provide more detail. One of the things noted in the ETL dataframes is that there was a column for Verified Purchases

![helpful votes df](https://github.com/BPeaver/Amazon_Vine_Analysis/blob/main/Images/helpful%20votes%20df.png)

This analysis would benefit from being further refined to only show verified purchases. It's safe to assume Vine reviewers are legitimate users, since they are given the product, but filtering down the data to only show Non-Vine users we could then compare actual verified purchasers and remove any fake or untrue reviews. 
