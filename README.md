# Amazon Vine Analysis
## Overview
As the first data expert at BigMarket, a startup company that helps businesses optimize their marketing efforts, I am required to assist one of BigMarket’s clients SellBy to run some hefty analytics. SellBy is about to release a large catalog of products on a leading retail website. They want to know how the reviews of their products compare to the reviews of similar products sold by their competitors. Aside from this, they also want to enroll in a program that gives out free products to select reviewers, but they would want to know if it is worth the cost.
I will be analyzing Amazon reviews written by members of the paid Amazon Vine program. The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. SellBy has paid a small fee to Amazon and provided products to Amazon Vine members, who are required to publish a review.

In this project, 50 datasets of product categories are available to chose from. I chose to analyze reviews in the Camera category. I used PySpark to perform the ETL process to extract the dataset, transform the data, connect to an AWS RDS instance, and load the transformed data into pgAdmin. Next, using PySpark, I determined if there is any bias toward favorable reviews from Vine members in the dataset.

## Results 
The raw camera dataset had 1801974 rows. I created a Vine data frame which had columns review_id, star_rating, helpful_votes, total_votes, vine, and verified_purchase". I filtered this dataframe based on reviews that had more than 20 total votes, and at the same time have the number of helpful votes divided by the number of total votes being equal to or greater than 50%. This reduced the number of rows to 51129. The resulting table is shown below:

![image1](https://github.com/GerlechJen/Amazon_Vine_Analysis/blob/main/Images/helpful_votes.png)

The data frame above was further filtered into two to obtain a Vine data frame where a review was written as part of the Vine program and a non Vine data frame where the review was not part of the Vine program. The vine data frame is shown below:


![image2](https://github.com/GerlechJen/Amazon_Vine_Analysis/blob/main/Images/vine%20data%20frame%20.png)

Below is the non Vine dataframe:
![image3](https://github.com/GerlechJen/Amazon_Vine_Analysis/blob/main/Images/non%20vine%20data%20frame%20.png)

The total number of reviews for the Vine and non-Vine programs were found next. Both counts are shown below:

![image4](https://github.com/GerlechJen/Amazon_Vine_Analysis/blob/main/Images/Vine%20count.png)

![image5](https://github.com/GerlechJen/Amazon_Vine_Analysis/blob/main/Images/non%20Vine%20count.png)

* From the above tables we can see that there were 607 Vine reviews and 50,522 non-Vine reviews.

Next I found the number of 5-star reviews for both paid and unpaid reviews. The results are shown below:

![image6](https://github.com/GerlechJen/Amazon_Vine_Analysis/blob/main/Images/5-star%20paid.png)

![image7](https://github.com/GerlechJen/Amazon_Vine_Analysis/blob/main/Images/5-star%20unpaid.png)

* As it can be seen from the 2 tables, out of the 607 Vine reviews, 257 were 5-stars reviews and 25,220 out of the 50,522 non-Vine reviews were 5 stars reviews.

Finally, the percentage of Vine and non Vine reviews that were 5-star were calculated. 

![image8](https://github.com/GerlechJen/Amazon_Vine_Analysis/blob/main/Images/percentage_paid.png)

![image9](https://github.com/GerlechJen/Amazon_Vine_Analysis/blob/main/Images/percentage_unpaid.png)

* As it can be seen, 42.3% of Vine reviews were 5 stars and 49.9% of non-Vine reviews were 5 stars.


## Summary 
From the results given, there isn't any positivity bias for reviews in the Vine program. This is because the percentage of 5-star reviews for the Vine program was less compared to the percentage of 5-star reviews for the non-Vine reviews. 
This conclusion can be further examined by finding the percentage of all stars(1,2,3,and 4 stars) for both paid(Vine) and unpaid(non Vine) reviews. Aside from that this same analysis can be performed on a few more different categories of products for a more thorough analysis.


----

**Completed by:** Jennifer Anno-Kusi

**Email:** jannokusi@gmail.com 


