# <u> Book Recommendation System </u>


### <u> Project Overview: </u>

* Today, recommender systems have become a central part of how businesses market their products to their customers. By analyzing the historical usage behavior of a user as well as that of the people in a their network, businesses are able to accurately predict what products will be of interest to a particular user.

* While recommender systems are now well developed in areas such as Music, Videos and Movies, E-commerce, Internet search results through companies like Google, Netflix, YouTube, Amazon, Spotify among others, lesser work has been done in Book Recommendation systems.

* If we analyze how people look for and buy books, suggestion are mostly done through person-to-person interactions, or reading through a large number of reviews. This not only results in a bias and time consumption, users also loose out on opportunity to use their exposure to a vast network readers all over the world. Such recommendation system could also be used by institutions like libraries, to help library staff make more accurate suggestions


### <u> Data Sources: </u>

Our Data consists of 2 sources over 5 files:
1. Book recommendation dataset
  a. Books.csv: This is the main file, which contains Book ISBN, Title, Author, Publishers etc.
  b. Ratings.csv: This is the ratings data of each user
  c. Users.csv: This contains demographic information of each user
  
2. Amazon Book reviews dataset
  a. Books_rating.csv: This file has information about book reviews for unique book and users who gives these reviews for each book.
  b. books_data.csv: This file contains the details of books such as genres, authors, cover, description and etc.

### <u> Data Cleaning and Initial Processing: </u>

1. The books dataset consists of ~271k books. The number of users are ~278k
2. The book data is merged on the ratings data using ISBN field, to create a Book-Rating database
3. The resulting database is then checked for any null values, and if present, those records are dropped
4. EDA


### <u> Algorithms Used: </u>

We have implemented 4 algorithms for this recommendation system:

1. Popularity based filtering
2. Item based collaborative filtering
3. User based collaborative filtering
4. Content based filtering


#### <u> Popularity based filtering: </u>

Based on which books are popular, this system suggests novels for you to read. The number of ratings and their median score are computed for each book. The Bayesian average is used to determine a popularity score using these two numbers.

#### <u> Item based filtering: </u>

Item based collaborative filtering involves analyzing past behavior of a user towards items that they have already rated and then recommending items that are similar to the used items. The first step involves creating a User-Item similarity matrix. From this matrix, we can see which items are most similar to which other items. Now based on items already rated by the user, we recommend the most similar items.

#### <u> User based filtering: </u>

User-based collaborative filtering involves analyzing the past behaviour of various users towards items that they have already rated and then recommending items that are similar to the other users' items. The first step involves creating a User-Item similarity matrix. From this matrix, we can see which users are most similar to which other users. Now based on items already rated by a user, we recommend the items which are also rated higher by other similar users.

#### <u> Content based Recommendation System: </u>

Collaborative filtering has the disadvantage that users repeatedly receive recommendations of the same type, and as they act on these recommendations, they repeatedly receive recommendations of the same type. The main distinction in content-based filtering is that we don't employ a User-Item matrix. Instead, we create a feature vector based on different features for each item and use similarity metrics to compare it to other titles to generate recommendations.
