# Amazon_Vine_Analysis
## Overview
$ellBy is interested in participating in an Amazon Vine program that offers incentives for users who submit Amazon Vine reviews of any $ellBy products. Big Market has been hired by $ellBy to determine if the program is worth the cost. The purpose of this project is to download a video game review dataset, use PySpark to perform the ETL process, upload the data to an AWS RDS instance in PostgreSQL, and perform an analysis in order to determine if there is any bias towards $ellBy products from paid Vine members, based on their reviews.  
## Resources


Applications/Technologies:

-	ETL (Extract, Transform, Load)
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
![paid_review](https://github.com/JoseEspinosaTello/Amazon_Vine_Analysis/blob/main/Resources/paid_review.png)
-	There was a total of 94 video game reviews from paid users.
-	There was a total of 48 five-star reviews from paid users.
-	A total of 51% of paid users returned a five-star review.

Non-Paid Vine User Reviews:
![nonPaid_review](https://github.com/JoseEspinosaTello/Amazon_Vine_Analysis/blob/main/Resources/nonPaid_reviewpng.png)
-	There was a total of 40,471 video game reviews from non-paid users.
-	There was a total of 15,663 five-star reviews from non-paid users.
-	A total of 39% of non-paid users returned a five-star review.

## Summary

The analysis shows us that there is an 11% difference in five-reviews as paid Vine users have a 51% five-star rate and non-paid Vine users have a 39% five-star rate. This means there is a small bias on the paid Vine user side, as paid users may be submitting reviews for the incentives, however, there is not enough evidence to make a conclusion. While there is a higher percentage of paid users submitting five-star reviews, the amount of paid users submitting these reviews is considerably lower, which can create skewed results.

In order to help determined if the five-star reviews are skewed it would be beneficial to compare the four-star reviews as well.
![bucket](https://github.com/JoseEspinosaTello/Amazon_Vine_Analysis/blob/main/Resources/4star.png)

The four-star reviews seem to trend in the same direction as paid users have a higher percentage of four-star reviews at 26%, compared to non-paid users sitting at 17%. This once again shows a bias towards paid users, compared to the five-star reviews. The final analysis we can perform is a Natural Language Processing (NPL) analysis on the review comments. Using NPL we can analyze the comments to determine if they are genuine, a script, or less than genuine. NPL would allow our team to combine all results and make a final assesment on the bias of the user reviews.

## Process

-	Create an AWS S3 bucket and upload the Game Review Dataset

	AWS Bucket:
	![bucket](https://github.com/JoseEspinosaTello/Amazon_Vine_Analysis/blob/main/Resources/bucket.png)

	Bucket Game Review Dataset:
	![dataset](https://github.com/JoseEspinosaTello/Amazon_Vine_Analysis/blob/main/Resources/dataset.png)

-	Create AWS RDS database

	AWS Database:
	![database](https://github.com/JoseEspinosaTello/Amazon_Vine_Analysis/blob/main/Resources/database.png)

-	Add database to PostgreSQL and create tables

	PostgreSQL AWS challenge database 

	![postgresql](https://github.com/JoseEspinosaTello/Amazon_Vine_Analysis/blob/main/Resources/postgresql.png)

	SQL schema:

	![schema](https://github.com/JoseEspinosaTello/Amazon_Vine_Analysis/blob/main/Resources/schema.png)

-	Perform ETL process using Pyspark and load data to database (Amazon_Reviews_ETL.ipynb)

	Import data from source:
	![importData](https://github.com/JoseEspinosaTello/Amazon_Vine_Analysis/blob/main/Resources/importData.png)

	Create tables(vine_table): 
	![vineTable](https://github.com/JoseEspinosaTello/Amazon_Vine_Analysis/blob/main/Resources/vineTable.png)

	Load to database:
	![connection](https://github.com/JoseEspinosaTello/Amazon_Vine_Analysis/blob/main/Resources/connection.png)

	![loadVine](https://github.com/JoseEspinosaTello/Amazon_Vine_Analysis/blob/main/Resources/loadVine.png)

-	Perform analysis (Vine_Review_Analysis.ipynb):

	Read vine_table from database and create a dataframe:
	![readDataframe](https://github.com/JoseEspinosaTello/Amazon_Vine_Analysis/blob/main/Resources/readDataframe.png)

Final analysis:
![paid_review](https://github.com/JoseEspinosaTello/Amazon_Vine_Analysis/blob/main/Resources/paid_review.png)

![nonPaid_review](https://github.com/JoseEspinosaTello/Amazon_Vine_Analysis/blob/main/Resources/nonPaid_reviewpng.png)