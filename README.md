# Movie-Recommendation-System
### Problem Definition:
This is a mobile application backed by a recommendation engine that will be useful to anyone who is looking to find movies similar to the movies they have watched and rated. Applications like Netflix, are backed by recommender systems running on large amounts of data. These services can recommend and stream content that they have access to.
In this application, there is a large collection of movies from all popular genres and several popular languages. In this system, the important difference is that users are not provided with a link to watch the movie but are directed to the official IMDB page of the movie. Here the user can get to know the complete details of the top 5 recommendations for them so that they only invest their time in learning about these recommended movies.

### Implementation details:

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
