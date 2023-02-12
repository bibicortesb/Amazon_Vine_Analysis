# Amazon_Vine_Analysis

## Project Overview
Sellby is interested in what Big Data has to offer. Along with Jennifer I developed a project that shows a quick overview of Big Data potencial by performing ETL Amazon Product Reviews to find valuable information.

### Purpose

In this project I will select a Music dataset to perform an ETL process, transform the data, connect to an AWS RDS instance and load the data in pgAdmin. By doing this, further analysis can be done in order to obtain valuable information such as bias of Amazon reviews.   


## Resources

- Data Source: https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Music_v1_00.tsv.gz
- Software: Google Colab & pgadmin. 

## Results

### Data Transformation
The first step was perform an ETL process to save four DataFrames in pgAdmin, linked with an RDS in AWS. 

Below, there is the datframe used in the anlysis. 

![image](https://user-images.githubusercontent.com/114015620/218261641-12c04c58-85f7-451f-bc67-22d51f1775b3.png)

Over this data frame several filtering operations were used to save reviews with total_votes >= 20. 
![image](https://user-images.githubusercontent.com/114015620/218265619-7360669a-532c-44de-a5fc-9fc19301d468.png)

Next, a dataframe with th helpful ratio column was created. 

helpful_ratio = helpful_votes / total_votes 

![image](https://user-images.githubusercontent.com/114015620/218265669-8de32e44-01a0-4b72-b32d-30fdb0b9f625.png)


### Paid program reviews

A new data frame was formed with all the reviews that were written as part of the Vine program. 

![image](https://user-images.githubusercontent.com/114015620/218265777-1a0a9c0d-1196-472a-8452-314f46676858.png)

It was found that 85,827 of the reviews were paid. 

![image](https://user-images.githubusercontent.com/114015620/218265877-e3419261-fd2b-4c26-9a9a-277d6429d6ca.png)

From the paid ones, 0% of them wew 5 star reviews.

![image](https://user-images.githubusercontent.com/114015620/218265933-9e79c35c-c6f3-43f2-965f-756ab4007e1e.png)


### Unpaid program reviews
A separete data frame with all the reviews that were not part of the Vine program. 
![image](https://user-images.githubusercontent.com/114015620/218265842-a01ad01f-ef68-4757-9993-68522a1f49ba.png)

It was found that 85,821 of the reviews were unpaid.

![image](https://user-images.githubusercontent.com/114015620/218265991-d246bc89-4a86-408b-a355-eda2ff663ff4.png)

Out of these reviews, 58,315 --> 67.94% of the unpaid were 5 star reviews.

![image](https://user-images.githubusercontent.com/114015620/218266038-8b7742ae-888e-45ec-b547-4a683e9de8d4.png)



## Summary 

Through the analysis, reviews from the vine program were filtered to have a numerical value of the amount of reviews with 5 stars that were paid and unpaid. After this, it can be said that there is no bias on the reviews. In the vine programm there is 0%, 5 star reviews. On the other hand, the non-vine program reviews show a 67.94% of 5 star reviews. In the music data set it can be concluded that paid 5-star reviews did not contribute to the bias of the result.  

It is interesting to mention that this code works on every dataset of the reviews since they all share the same structure. The exact same analysis can be perform in other categoris such as movies or books. It is amazing to develop tool that enable reproducibility if data structures are consistent. Additionally, there is still a lot that can be performed with this data set. By filtering the range 0-2 stars, it could even be determined if there's a bias for bad rates. Furthermore, in a different case where bias is present, we can evalaute with a t-test if there's a statistical difference between the means of 5 star rating paid and unpaid reviews. Certainly with the correct research question, the potential of Big Data is huge, as Sellby may discover. 



 



