Project Members : Tim Hugele, Mark

Project Goals: 

1) Find a relationship between movie success, measured by IMDb Score and Worldwide Lifetime Revenue, and the runtime
    of movies.
    
2)

Navigating the Respository

Methods:

1) The data was obtained from https://www.kaggle.com/carolzhangdc/imdb-5000-movie-dataset. This data set included 5,000 movies from IMDb.com. After downloading the dataset, the first thing we did was look at the data set and determined which categories we wanted to keep. 

Choosing Categories to Use

We decided not to work with either people's names, so we deleted all three actor name categories and the director name category. We also thought that it might be interesting to see how movies performed based on the popularity of the director and top billed actor, irrespective of their names, so we kept the categories pertaining to their Facebook likes. 
We also dropped the columns that contained links, posters, and the aspect ratio because we didn't think that we could do anything with those fields. We also dropped the fields that were already covered in the other data sets, except for the movie titles so that we could use that field for the merge. 
We dropped budget because of the large amount of missing data. 
Finally, we also dropped the categories related to the number of critic and user reviews because we didn't think that it was particularly useful.

After this step we renamed the columns by capitalizing and removing underscores in an attempt to make the column names look like titles. 

Cleaning the Data

We then started to look for null values.
For MPAA ratings, we took all of the null values and renamed them Not Rated. We also took all of the Unrated movies and renamed them Not Rated so that we could have one category for movies with a missing rating.
For country, language, and color we took the null values and labelled them unknown.
For runtime, we dropped all of the movies that contained no runtime. We did this because we wanted to look at the statistics for this category and didn't want to alter the data by assigning it to the mean, median, or mode.
We also deleted the movies without Director Facebook Like counts.

Duplicates

We then looked for duplicates in the data. However, we wanted to be careful not to remove duplicate movie titles that were actually different movies; sequels, for example. We did that be looking for movies that were duplicated by both title and release year. We then removed those duplicate movies. In order to differentiate the movies that were sequels, we added the release year to the movie title. This way, when merging our two data sets on the movie titles we wouldn't have the probablem of having identical names to merge, which creates problems. 

Merging

We then merged our data.

Analyzing the Data

1) Runtime vs. IMDb Ratings

After merging our data, one of the relationships that we wanted to look at was how the runtime of movies affected their success at the box office and with audiences. The metrics we looked at for the box office were Worldwide Lifetime Gross and IMDb Ratings.

We found that the average runtime of a movie in our dataset was approximately 117 minutes, just under two hours, and the median was 115 minutes. This indicates that there the data is slight skewed right. This makes sense because it is probably more likely to have epic movies that are over three hours than there are movies that are under one hour. After creating a histogram and a box plot the right skew of the data was confirmed. 

We then looked at the IMDb ratings and found that the average rating was about 6.75 and the median was about 6.7, indicating a slight right skew. However, unexpectedly the ouliers were actually all concentrated on the low end of the scale. This is probably the result of having relatively few low rating outliers on the low side with more high ratings that fall just short of being considered outliers. 

When took the average IMDb score of runtimes that were over 117 minutes and those that were below 117 minutes. We found that the average rating for a movie under was about 6.45 and over was about 7.13. This indicates that movies over 117 minutes are rated approximately .68 points better on average. We also found the standard deviation to be about 0.888 for below and 0.862 for movies above 117 minutes. This indicates that the spread of ratings is slightly lower for longer movies, indicating slightly more confidence in the expected rating when making a movie. 

We also found there to a correlation of approximately 0.407. This indicates that there is a moderate positive correlation in the data. We also tested the data having removed the outliers, and the relationship still holds. The correlation increased to 0.411.

Runtime vs. Worldwide Lifetime Gross

We then did the same analysis comparing Runtime with Worldwide Lifetime Gross. We found the average gross for these movies was approximately $312 million and the mean was approximately $222 million. This indicates as pretty strong right skew. Because of this, we then did the same analysis after removing the outliers. When we did this, we found the mean to be about $254 million and the median to be about $212 million. Now the data is skewed left, but it is better than before. Therefore, we continued our analysis with this data set. 

We found the movies with below average runtimes to average about $248 million and with above average runtimes to be about $262 million. This shows that movies that are longer than average tend to gross about $14 million more in gross revenue than shorter ones. However, we found the correlation to a weak 0.081. This contrasts with the correlation from before we removed the outliers of about 0.261.

2) 
  
Summary of Results

1) We found that movies that had longer runtimes tended to receive both higher IMDb ratings and Worldwide Lifetime Gross Revenues, though the correlation was higher with IMDb ratings, 0.407, than with Revenues, 0.081.

Conclusions from Results

This data shows that longer movie runtimes are correlated with better IMDb scores and slightly higher Revenues. I think this may be for a few reasons. One is that, movie execs probably expect viewers to be less interested in watching longer movies. This may result in them being pickier with movies that are pitched to them that have long run times. As a result, the bar for movies being approved is higher for longer movies they usually end up being better movies that will receive higher IMDb ratings. 

I would argue that budget data would be useful for further investigations of the this question. This would useful information because a longer movie will probably cost more to make as a result of having to pay people more for having done more work. Therefore, since longer movies are correlated that strongly with greater revenue, it seems likely that longer movies might have a lower return on investment. 