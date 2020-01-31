# Executive Summary

Our first strategy is to finalize a good reddit source for comparing the two popular sports Soccer and Cricekt. While most of us think Soccer as the most popular sports, data told us a different story. Cricket is played around 50 countries with 2.5 billion fans while football is played in over 200 countries with 3.5 billion fans! In other words per country there are 50 million cricket fans compared to 17.5 million football fans. It was a challenge to get a correct key word for the amount of data that we needed.
Intially I was having issues in getting enough data (our target was close to 2000 records in each subreddit). I had to change the day window to attain this objective. Once I adjusted the day window to 15 and appropriate fequency I was able to collect enough data for training our models.

After extracting the blog post data next decision we had to make was what column or columns needs to be my X. We were inclined to use 'Title' and 'Self text' consdering the relevance of the contents. But after reviewing the shape of data and Null values we have decided to use only 'Title' as 'Self Text' was not adding much value in training my model.  

EDA helped me set up a preprocessing plan for our model. For preprocessing, I had created a fucntion that used regex, lemmatizatizer which removed punctuation and stopwords. For modeling, I used  TFIDF and Count vetorizers. They brought context of word choices into play, which will give us a better understanding of the group of words used in a reddit blog post about the sports we are analyzing.
 
Machines had no problem understanding the blog posts, after using vectorizers.


# Problem Statement

ESPN has hired DevJee Inc. to address a data collection issue in their market research team. The market research team is responsible for analyzing and compiling online fan participation in two major sports viz. Cricket and Soccer. The feeds are coming from Subreddit blogs. The issue we are facing is the team of interns that collects the data doesn't have much idea of these sports and mixes the blogs before passing it to the research team. We are tasked to come out with a solution that correctly identifies the type of blogs.

 - We will be using Using Pushshift's API to collect the data from subreddits of Cricket and Soccer.
 - We will use NLP to train a classifier on which subreddit a given post came from.
 
 # Conclusion and Recommendation
 
## Conclusions : 
Using Pushshift's API we have successfully collected data from two of the subreddits viz. Cricket and Soccer. After doing the initial cleanup we have concatenated the dataframes to be used for training the model. During the EDA we were able to find the most engaging posts,trend of the daywise engagement from Fans and most frequent words. Using NLP we have trained our classifiers. We have calaculated Base Line Score (Section 5.1), Logistic Regression Model score (Section 5.2 and 5.3), Gaussian NB Model (Section 5.4), Multinomial NB (Section 5.5) and Random Forest Model(Section 5.6) during our modeling process. We have used Count Vectorizer and TFIDF Vectorizer in our models.

All the models we have trained outperformed the Base Line model. TFIDF vector with Logostics Regression had the best Train and Test score. The scores were 0.92 on the Train Score and 0.88 on the Test score.

## Recommendations :

While our mdel trained on Logistic Rgression with TFIDF vectorizer performed better than other models we still think there is a scope of improvement in the accuracy of the models. The present model is also slightly overfit. If we can get more data with different source other than Reddit we will be able to better train our classifiers. We will also like to train our models on other classifiers like Decision tree and Support Vector machines.