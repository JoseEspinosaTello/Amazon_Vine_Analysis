# Amazon_Vine_Analysis
## Overview
$ellBy is interested in participating in an Amazon Vine program that offers incentives for users the submit Amazon Vine reviews of any $ellBy products. Big Market has been hired by $ellBy to determine if the program is worth the cost. The purpose of this project is to download a video game review dataset, use PySpark to perform the ETL process, upload the data to an AWS RDS instance in PostgreSQL, and perform an analysis in order to determine if there is any bias towards favorable reviews from Vine members towards $ellBy products.  
## Resources


Applications/Technologies:

-	ETL (Exract, Transform, Load)
-	Python
-	Google Colab
-	PySpark
-	AWS RDS, S3
-	PostgreSQL

Video Games Dataset AWS Source: 

-	https://jchallenge-bucket.s3.amazonaws.com/amazon_reviews_us_Video_Games_v1_00.tsv.gz



## Results
Our dataset was the total video game reviews of Amazone Vine paid and non-paid users. The users reviewed serveral video games on a five-star scale. The analysis is broken into the two groups: paid users and non-paiid users. We will determine if there is a bias based on the two types of reviewing users.

Paid Vine User Reviews:
![bucket](https://github.com/JoseEspinosaTello/Amazon_Vine_Analysis/blob/main/Resources/paid_review.png)
-	There was a total of 94 video game reviews from paid users.
-	There was a total of 48 five-star reviews from paid users.
-	A total of 51% of paid users returned a five-star review.

Non-Paid Vine User Reviews:
![bucket](https://github.com/JoseEspinosaTello/Amazon_Vine_Analysis/blob/main/Resources/nonPaid_reviewpng.png)
-	There was a total of 40,471 video game reviews from non-paid users.
-	There was a total of 15,663 five-star reviews from non-paid users.
-	A total of 39% of non-paid users returned a five-star review.

## Process

-	Create an AWS S3 bucket and upload Dataset

AWS Bucket:
![bucket](https://github.com/JoseEspinosaTello/Amazon_Vine_Analysis/blob/main/Resources/bucket.png)