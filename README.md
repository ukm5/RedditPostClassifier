# Project 3 - Reddit classifier

## Part A) Extracting data from subreddits to create ML models using NLP
## Part B) Using NLP to make ML classification models

### Problem statement: 
##### Extracting data from the `tea` and `Coffee` subreddits using API wrapper PRAW, as outlined by Reddit. A maximum of 1000 posts maybe obtained using API requests, and for the subreddits modeled in this projects, two data sets of approximately 1000 posts must be obtained. Developing a subreddit classifier for `tea` and `Coffee` posts using various ML classification models to identify the best combination of hyperparameters using Gridsearch and Pipelines. 

### Executive summary:
##### Extracted data from the `tea` and `Coffee` subreddits using API wrapper PRAW, as outlined by Reddit. A maximum of 1000 posts maybe obtained using API requests, and for the subreddits modeled in this projects, two data sets of approximately 1000 posts were obtained. From the Reddit data sets for the two subreddits, data was cleaned, explored, and analysed before using them to develop ML classification models. Also, the data was analysed for any correlations or interesting patterns.

## Contents

- [Data extraction using PRAW in `RedditAPI_and_data_acquisition.ipynb`](#)
- [Exploratory Data Analysis and data visualization](#Exploratory-Data-Analysis)
- [Baseline accuracy](#Baseline-accuracy)
- [Model Development: Different classification models](#Developin-the-statistical-and-machine-learning-models)
- [Looking at subreddit vector alignment](#Attempt-at-creating-vectors-and-testing-for-alignment)
- [Conclusions and Recommendations](#Conclusions-and-Recommendations)

## Data Dictionary

Data dictionary for the dataframes relevant to this project:

|Column Name|Type|Description|
|---|---|---|
|`title`|string|Post title in subreddit|
|`subreddit`|string/int|Id reference to the subreddit|
|`created`|datetime|Time of creation of the post|
|`score`|int|Number of upvotes on the post|
|`is_self`|bool|The post contains a body of text|
|`id`|object|Id of the user that posted|
|`rank`|int|Rank of the post in the list|
|`selftext`|string|Body of the post, if present. NaN otherwise.|

All data using PRAW API wrapper and [Kaggle](#https://www.reddit.com/)

## Conclusion and Recommendations

For the data obtained and analyzed, the following inferences and conclusions were made:

* Contrary to initial expectations, there is little to no correlation of upvotes and posts to creation time
* There is dedicated coffee and tea members posting in their respective subreddits
* There are both common and unique words to each subreddit. The unique words are often names of different kinds of the beverage that subreddit is referring to or names of places they are grown in
* Various models were fitted and their scores were compared. The tree classifiers tend to offer higher accuracy while being robust
* Logistic Regression models seemed to perform on the same level of accuracy as tree models
* Models showed significant improvement of accuracy scores from baseline of 50% to more than 85% using classification models
* A vector space model was attempted at to obtain basis vectors for each subreddit in a rather crude fashion but showed significant separation of vectors, showing close to orthogonality of the two subreddit spaces

The objective of project was to compare various classification models and towards that various kinds of models were fit and compared while optimizing the hyperparamters. Also, a rudimentary vector space analysis was done and shown to have significance as a possible classifier.