# <u> Book Recommendation System </u>


### <u> Project Overview: </u>

* Today, recommender systems have become a central part of how businesses market their products to their customers. By analyzing the historical usage behavior of a user as well as that of the people in a their network, businesses are able to accurately predict what products will be of interest to a particular user.

* While recommender systems are now well developed in areas such as Music, Videos and Movies, E-commerce, Internet search results through companies like Google, Netflix, YouTube, Amazon, Spotify among others, lesser work has been done in Book Recommendation systems.

* If we analyze how people look for and buy books, suggestion are mostly done through person-to-person interactions, or reading through a large number of reviews. This not only results in a bias and time consumption, users also loose out on opportunity to use their exposure to a vast network readers all over the world. Such recommendation system could also be used by institutions like libraries, to help library staff make more accurate suggestions


### <u> Data Sources: </u>

Our Data consists of 3 files:

1. Books.csv: This is the main file, which contains Book ISBN, Title, Author, Publishers etc. 

2. Ratings.csv: This is the ratings data of each user

3. Users.csv: This contains demographic information of each user

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

This system recommends books based on the which books are in trend. For each book, the number of ratings received and their median value is calculated. Using these two numbers, a popularity score is calculated using Bayesian average.

#### <u> Item based filtering: </u>

Item based collaborative filtering involves analyzing past behavior of a user towards items that they have already rated and then recommending items that are similar to the used items. The first step involves creating a Item-Item similarity matrix. From this matrix, we can see which items are most similar to which other items. Now based on items already rated by the user, we recommend the most similar items.

#### <u> User based filtering: </u>

A drawback of item based collaborative filtering is that a users keeps on getting recommendations of a same type, and as the user uses these recommendations, they again get recommendation of the same type. This drawback can be overcome by using User based collaborative filtering. The first step involves creating a User-User similarity matrix. From this matrix, we can see which users are most similar to which other users. Now based on items already rated by a user, we recommend the items which are also rated higher by other most similar users.

#### <u> User based content filtering </u>

This technique is similar to Item based filtering, in that it involves analyzing history of a single user. The key difference however is that it uses individual item features, instead of creating a item-item matrix. By analyzing how a user rated different items and their feature values, a rating score is calculated for other items. Recommendations are then created based on these individual item scores.