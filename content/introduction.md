---
 layout: default
 title: What is Sentiment Analysis?
 parent: Outline
 nav_order: 11
---
# What is Sentiment Analysis? A Brief Introduction

## Definition
>“Sentiment analysis or opinion mining is the computational study of people's opinions, sentiments, evaluations, attitudes, moods, and emotions.” 
>
>Bing Liu,  _Many Facets of Sentiment Analysis._   [A practical guide to sentiment analysis (2017)](http://resolve.library.ubc.ca/cgi-bin/catsearch?bid=8790457). 


## Common Types of Sentiment Analysis

1. **Standard sentiment analysis**\
One of the basic tasks in sentiment analysis is to determine whether the opinion in a piece of text is positive, negative, or neutral. This value is called polarity.  A text can be analysed at the document, sentence, or feature/aspect level. The overall sentiment of a text is determined by its polarity score.
![Standard Sentiment Analysis example](/content/images/basic-sentiment.png)

An example of a dataset of standard binary sentiment analysis is the [IMDB Movie Reviews Dataset](https://www.kaggle.com/lakshmi25npathi/imdb-dataset-of-50k-movie-reviews) 
* collection of 50,000 movie reviews from IMDB
* binary - values are positive or negative only


2. **Fine-grained Sentiment Analysis**\
This type of sentiment analysis is also polarity based, but it uses additional discrete classes to obtain more granular results. 
It is much more challenging! Emotions are subjective and as more discrete categories are added, it can be hard to pin down whether something is negative or very negative.
![Fine Grained Sentiment Analysis Example](/content/images/fine-grained-sentiment.png)

An example of a dataset of fine-grained  sentiment is the [Stanford Sentiment Treebank](https://nlp.stanford.edu/sentiment/treebank.html).
* original data from Rotten Tomatoes 
* Sentence-level corpus (10,662 sentences)
* Fully-labeled trees
* 5 discrete categories
![Stanford Sentiment Treebank](/content/images/stanford-sentiment.png)

3. **Emotion detection (ED)**\
More advanced sentiment analysis goes beyond polarity to detect and analyse the emotions that underlie a text. It makes associations between words and emotions like anger, disgust, happiness, frustration, surprise etc.
Emotion detection requires defining the model of emotion to be used. Emotion models define how emotions are represented.

Let's look at two main types of emotion models:

**Discrete emotion models (DEMs):** 
The discrete model of emotions places emotions into distinct classes or categories. 
One example is Plutchik's wheel of emotions.
![Plutchik's wheel of emotions](/content/images/Plutchik_wheel_of_emotions.png)
Plutchik, Robert. "A Psychoevolutionary Theory of Emotions." Social Science Information, vol. 21, no. 4-5, 1982, pp. 529-553.

**Dimensional emotion models (DiEMs):**
The dimensional model shows that there is a relation between emotions; they are not independent. 
One example is Russell & Mehrabian’s 3‐dimensional emotion model of affects
![dimensional emotion model](/content/images/Dimensional_emotion_model.png)

Russell, James A., and Albert Mehrabian. "Evidence for a Three-Factor Theory of Emotions." Journal of Research in Personality, vol. 11, no. 3, 1977, pp. 273-294.

An example of a dataset of emotion detection is the [SMILE Twitter Emotion dataset](https://www.kaggle.com/ashkhagan/smile-twitter-emotion-dataset).
* 3085 tweets from 13 Twitter handles affiliated with visitors to the British Museum
* created for the purpose of classifying emotions, expressed on Twitter towards arts and cultural experiences in museums.
* 5 emotions: anger, disgust, happiness, surprise and sadness

4. **Feature or Aspect-Based Sentiment Analysis**\
A text can contain multiple sentiments. A standard binary positive/negative analysis does not reflect these differing sentiments expressed in different aspects of a single text. 

In aspect-based sentiment analysis, texts are dissected to identify the features (or aspects) of a product that are discussed and the sentiments expressed about these features or aspects. 
For example, a restaurant reviewer may love the food but be frustrated with the service. 


![feature based sentiment](/content/images/feature_based_sentiment.png)

## Sentiment Analysis Across Disciplines


## Limitations and Pitfalls

## Sample Sentiment Analysis Projects

**NaSent – Stanford's Neural Analysis of Sentiment**
Analyzes sentences from movie reviews and gauges the sentiments they express on a five-point scale from strong like to strong dislike. Experiment with the online demo at <https://nlp.stanford.edu/sentiment/>


## Tools and Methods used for Sentiment Analysis

