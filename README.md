# Movie-Recommendation-System
### Problem Definition:
This is a mobile application backed by a recommendation engine that will be useful to anyone who is looking to find movies similar to the movies they have watched and rated. Applications like Netflix, are backed by recommender systems running on large amounts of data. These services can recommend and stream content that they have access to.
In this application, there is a large collection of movies from all popular genres and several popular languages. In this system, the important difference is that users are not provided with a link to watch the movie but are directed to the official IMDB page of the movie. Here the user can get to know the complete details of the top 5 recommendations for them so that they only invest their time in learning about these recommended movies.

### Implementation details:

The Movie Recommender System is served as a native Android application. Hence, the back-end and front-end are both pure java.

#### Back end:
The java classes are -
● SelectGenre.java - asks the new user to rate the genre specific movies and
send this data to rateMovie.java. This class uses the movie_metadata.csv file to
display genres contained in the list of movies.
● rateMovie.java - creates userId-to-movieId matrix from the ratings_edited.csv file
and then using item-to-item cosine similarity, rating of new user for each movie has been calculated. His top new calculated ratings for the movies has been shown as the recommended movies to the new user. This class also uses the movies_metadata.csv file.
● recommendedMovies.java - Shows the top 5 movies recommended to the user in the form of list view. Sends imdb ID to webActivity.java.
● webActivity.java - Gets the imdb ID of the movie and shows the Imdb page of the movie chosen.
● ourViewClient.java - Used to load the url on the same app page.
● Movie.java - Used to store the details of each movie and to create objects for
each movie.

