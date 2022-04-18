# Pratilipi_assignment
Collaborative Filtering 


For this assignment, I build a collaborative filtering recommending system using the library Surprise. The objective of the assignment was to reccomend 5 books that the users had never encountered before. First, I would like to mention that I had to scale down the datapoints of the parent csv, user-interactions. As this csv had over a 100 million datapoints, using all the data resulted in a memory error. After breaking the initial dataframe into chunks, I picked the top 106 users, whose collective readings yielded around a million data points and I reccommended 5 pratilipis to them, that they had not previously encountered (result.csv has these).


In the pre-processing, I grouped the dataframe by user id and aggregated them with counts of percent_read and sorted it to obtain a series which had the user id with the number of pratilipis that they had read. I used this to create a mask for the top users who had in cumulation, read a million datapoint and dropped the duplicates for a commong (user_id, pratilip_id) pair.   

I used the Singular Value Decomposition algorithm from the surprise package to predict these recommendations. As I ran into a lot of technical snags, namely issues regarding build tools from the Microsoft visual studio package for Windows, I could not properly cross-fold my dataset or evaluate my results. The high level understanding was to obtain predictions from the algorithm and pick only from the unique values of pratilipi_ids, the pratilipis that the 106 users had not read before.

This process could be made better in a number of ways. Mainly, by trying and evaluating more algorithms on the dataset and evaluating the results of each to find the appropriate model for the problem dataset. Another way could be by cross folding the dataset and holding a part for validation. A good baseline model for this problem could just be to return the most read pratilipis that the user has yet not encountered.
