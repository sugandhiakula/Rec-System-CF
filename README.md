# Rec-System-CF

_In collaboration with Rushya Puttam (@rushyaP)_.

The aim is to build a movie recommendation system by taking user ratings for nearly 100,000 movies
and make recommendations for movies that a user has not watched, based on the user's rating of other 
movies, and how similar users rate the movie being recommended.

Collaborative filtering is a simple but effective method for predicting how a user will rate a movie they 
haven't watched, based on how similar users rate the movie. Unlike the LFM method, collaborative filtering is
a non-iterative method, and does not require the optimization of any error functions.

The following steps sum up the item-item collaborative filtering process:
1. Select a similarity metric (the cosine/adjusted cosine similarity was used in this project)
	- The cosine similarity between two movies relies simply on the ratings of the two movies
	  across all users
	- The adjusted cosine similarity is similar to the cosine similarity, except that it takes
	  into account that different users have different rating schemes
2. Calculate the similarities across all the movies in the training dataset, using the above measures
3. The similarity measures can then be used to predict how a user will rate a movie that they haven't watched
	- The prediction was be calculated by dividing the 
		sum of (similarity of movie of similar movie*rating that the user gave the movie)
						by
		sum of similarities of all similar movies
4. The RMSE of predictions is then calculated by determining the difference in the predicted ratings and the actual ratings

The results from this model can be used to recommend movies to users, with an idea of how far the predicted rating might be from
the actual rating.