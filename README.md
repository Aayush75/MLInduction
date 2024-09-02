# MLInduction
This is the solution to the beginner track problem of the Machine Learning Club of the 'What The Hack' hackathon.

## Introduction

The first time I looked at this problem, it felt like it was impossible to do this in such a short period.

I started by reading a few articles in the resources file. The article on neural networks interested me a lot, so I took the time to thoroughly understand everything from it, even though it had a few math concepts I didn't know. 

A few of the questions I wanted to be answered by the dataset were:
1. How diverse is Netflix in terms of old and new movies/shows?
2. Is there a way to recommend movies/shows accurately using this dataset?
3. What is the overall age rating of movies/shows on Netflix?
4. What is the pattern of duration movies and number of seasons with release year?
5. How fast has Netflix's catalogue been increasing?
6. What is the average duration of movies and number of seasons by genre?
7. How does age rating vary with genre?

## Exploring, Cleaning and Analysing the Dataset

After loading the dataset on Jupyter Notebook, I used matplotlib and seaborn to visualise the data. Then I saw many inconsistencies with the data, such as - many empty entries, duration being a string, and multiple genres being separated by commas in a single string. So, I used one-hot encoding to convert genre, rating and type from categorical to numerical data. Then, I filled the empty spaces in the director column to 'Unknown' instead of deleting the rows because I would lose around 30% of the data by deleting rows. I did the same for cast and country as well. I dropped the rows with empty entries for date_added and rating.

Then, I calculated the mean, median, mode and standard deviations of the durations of movies and TV shows. However, this wasn't very useful for the analysis. I split movies into duration and TV shows into seasons by setting the duration of TV shows to -1 and the number of seasons of movies to -1. Once again, I plotted the graphs of release year vs duration/seasons to get a better look at the data.

## Movie/Show Recommender

I used content-based filtering to make a function that returns the top 10 recommended movies/shows based on the one you give the function. I used TF-DIF vectorizer to convert the cast and description into a format the machine could understand. Then, I used cosine similarity to find movies/shows similar to the input. However, I didn't find a way to check the accuracy of this data since I don't know most of the shows or movies that were recommended.

## Duration vs Release Year Predictor

I tried using linear regression to predict the duration of movies based on the release year. I split the dataset into training and testing (20%). However, the results from the model proved to be disappointing, with very high MAE and MSE values. I plotted the regression line on a duration vs release year graph and understood why regression might not have been the best algorithm for this.

## Conclusion

In the end, I plotted the graphs of average movie duration/number of seasons vs genre and the variation of rating with genre and its count to answer a few of the initial questions that still needed to be solved.

This hackathon was very fun, and most importantly, I learnt so many new things in such a short span of time.

I used ChatGPT for the code, and to solve my doubts regarding many concepts. However, I did not blindly copy paste anything, I typed all the code myself only after understanding it.
