# Movie-Recommendation-System
### Problem Definition:
This is a mobile application backed by a recommendation engine that will be useful to anyone who is looking to find movies similar to the movies they have watched and rated. Applications like Netflix, are backed by recommender systems running on large amounts of data. These services can recommend and stream content that they have access to.
In this application, there is a large collection of movies from all popular genres and several popular languages. In this system, the important difference is that users are not provided with a link to watch the movie but are directed to the official IMDB page of the movie. Here the user can get to know the complete details of the top 5 recommendations for them so that they only invest their time in learning about these recommended movies.

### Implementation details:

#### Movie Recommender System preliminary technique -  Item Based collaborative filtering
1. Get data from IMDB/Movie Lens or similar sources (must have ratings given by users to movies)<br />
2. Parse data to obtain Movie Identifiers and User Identifiers as well as the corresponding rating (at the least)<br />
3. Construct a matrix of User Id to Movie ID/Movie Name - each cell being a rating, null if no rating exists.<br />
4. Use the matrix in step 3 to calculate similarity/correlation scores of movies with one another (based on user rating vectors for each movie) - to construct an n x n correlation matrix. Each cell will contain the correlation score between the 2 movies to tell us how similar the ratings are (provided at least one user has rated both movies, if not the cell will contain a null value). <br />
        4.1 We could improve the results in step 4 by considering only those pairs of movies where we have a certain minimum number of users rating both. This number could be 50,100 or any number that gives us a decent sized non-null matrix ( provided it doesn’t end up being a sparse matrix)<br />
5. Create a test user and specify a few movies and corresponding ratings. Add this user’s ratings to the data set representation<br />
6. Get a list of recommended movies, for the test user, based on this vector <br />
For every movie in the list created in step 5 (i.e. every movie rated) 
- Get similar movies based on correlation matrix in step 4
- Scale similarity score by test user’s rating 
- Add movie and scaled similarity score to the list of recommended movies.<br />
7. If a movie appears more than once in the recommended list - ( means that it is similar to more than one movies in test user’s ratings vector ) - add up the scaled similarity scores in that case.<br />
8. Filter out movies that the test user has already watched. <br />

The Movie Recommender System is served as a native Android application. Hence, the back-end and front-end are both pure java.

#### Back end:
The java classes are -<br />
● SelectGenre.java - asks the new user to rate the genre specific movies and send this data to rateMovie.java. This class uses the movie_metadata.csv file to display genres contained in the list of movies.<br />
● rateMovie.java - creates userId-to-movieId matrix from the ratings_edited.csv file
and then using item-to-item cosine similarity, rating of new user for each movie has been calculated. His top new calculated ratings for the movies has been shown as the recommended movies to the new user. This class also uses the movies_metadata.csv file.<br />
● recommendedMovies.java - Shows the top 5 movies recommended to the user in the form of list view. Sends imdb ID to webActivity.java.<br />
● webActivity.java - Gets the imdb ID of the movie and shows the Imdb page of the movie chosen.<br />
● ourViewClient.java - Used to load the url on the same app page.<br />
● Movie.java - Used to store the details of each movie and to create objects for
each movie.<br />

![movierecommendersystem_classdiagram - page 1 1](https://user-images.githubusercontent.com/34748358/40587987-cfc2074e-61a4-11e8-9ac5-d32b989b68a3.png)

## Screenshots <br />
![1](https://user-images.githubusercontent.com/34748358/40590040-47939532-61c6-11e8-897c-97b4df36db43.png)
![2](https://user-images.githubusercontent.com/34748358/40590041-47a19664-61c6-11e8-901b-ec4c8b3f2446.png)
![3](https://user-images.githubusercontent.com/34748358/40590042-47b2987e-61c6-11e8-9cc1-0a44c39b3f81.png)
![4](https://user-images.githubusercontent.com/34748358/40590043-47c3deae-61c6-11e8-887c-a6813dd79a7c.png)
![5](https://user-images.githubusercontent.com/34748358/40590044-47d3dd7c-61c6-11e8-8ed8-807fcfedd326.png)
![6](https://user-images.githubusercontent.com/34748358/40590045-47ece20e-61c6-11e8-95d5-b81348d7ed1d.png)
