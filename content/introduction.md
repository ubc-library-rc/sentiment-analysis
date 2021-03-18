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

Sentiment analysis was first used to analyze brief communications that expressed an opinion. (Twitter, online reviews, etc.)
More recently, sentiment analysis has been applied to longer documents, including works of fiction. 

Give it a try using the [Sentiment viz: Tweet Sentiment Visualization](https://www.csc2.ncsu.edu/faculty/healey/tweet_viz/tweet_app/) demo. 
Type a keyword into the input field, then click the Query button. Recent tweets that contain your keyword are pulled from Twitter and visualized in the Sentiment tab as circles. 


## Common Types of Sentiment Analysis

** 1. Standard sentiment analysis**\
One of the basic tasks in sentiment analysis is to determine whether the opinion in a piece of text is positive, negative, or neutral. This value is called polarity.  A text can be analysed at the document, sentence, or feature/aspect level. The overall sentiment of a text is determined by its polarity score.

![Standard Sentiment Analysis example](/images/basic-sentiment.png)

An example of a dataset of standard binary sentiment analysis is the [IMDB Movie Reviews Dataset](https://www.kaggle.com/lakshmi25npathi/imdb-dataset-of-50k-movie-reviews)
* collection of 50,000 movie reviews from IMDB
* binary - values are positive or negative only

![Large Movie Review Dataset](/images/movie_review_dataset.png)


** 2. Fine-grained Sentiment Analysis**\
This type of sentiment analysis is also polarity based, but it uses additional discrete classes to obtain more granular results.
It is much more challenging! Emotions are subjective and as more discrete categories are added, it can be hard to pin down whether something is negative or very negative.
![Fine Grained Sentiment Analysis Example](/images/fine-grained-sentiment.png)

An example of a dataset of fine-grained  sentiment is the [Stanford Sentiment Treebank](https://nlp.stanford.edu/sentiment/treebank.html).
* original data from Rotten Tomatoes
* Sentence-level corpus (10,662 sentences) was then split  into  215,154 phrases
* Annotators indicated sentiment  and degree for up to 25 different levels of sentiment in 5 classes (very negative, negative, neutral, positive, very positive).

![Stanford Sentiment Treebank](/images/stanford-sentiment-trees.png)
NaSent - model trained on the SST data. [Try the live demo![(http://nlp.stanford.edu:8080/sentiment/rntnDemo.html)

** 3. Feature or Aspect-Based Sentiment Analysis**\
A text can contain multiple sentiments. A standard binary positive/negative analysis does not reflect these differing sentiments expressed in different aspects of a single text.

In aspect-based sentiment analysis, texts are dissected to identify the features (or aspects) of a product that are discussed and the sentiments expressed about these features or aspects.
For example, a restaurant reviewer may love the food but be frustrated with the service.

![feature based sentiment](/images/aspect_sentiment.png)

A sample project which uses aspect-based sentiment analysis is the [Aspect Extraction and Opinion Analysis](https://achyutjoshi.github.io/aspect_extraction/overview) project by Achyut Joshi, Ishika Arora, Sumedha Raman & Andrew Giannotto as a part of the CSE6242 course at Georgia Tech. Using various NLP models, the project aims to extract opinions regarding different aspects of a product from their Amazon product reviews, group them and determine the respective polarities. This allows users to find product reviews based on specific features of a product.

![amazon aspect extraction](/amazon_aspect_extraction.png)

** 4. Emotion detection (ED) **
More advanced sentiment analysis goes beyond polarity to detect and analyse the emotions that underlie a text. It makes associations between words and emotions like anger, disgust, happiness, frustration, surprise etc.
Emotion detection requires defining the model of emotion to be used. Emotion models define how emotions are represented.

Let's look at two main types of emotion models:

**Discrete emotion models (DEMs):**
The discrete model of emotions places emotions into distinct classes or categories.

**Dimensional emotion models (DiEMs):**
The dimensional model shows that there is a relation between emotions; they are not independent.

One example is Plutchik's wheel of emotions.
![Plutchik's wheel of emotions](/images/Plutchik_wheel_of_emotions.png)

Plutchik, Robert. "A Psychoevolutionary Theory of Emotions." Social Science Information, vol. 21, no. 4-5, 1982, pp. 529-553.

A sample humanities project which uses emotion analysis is  [Measured Unrest in the Poetry of the Black Arts Movement](https://scholarslab.lib.virginia.edu/blog/measured-unrest-in-the-poetry-of-the-black-arts-movement/) which 
analyzes the expression of emotions in the poetry of the Black Arts Movement of the 1960s and 1970s and looks at how the feelings associated with injustice are coded in terms of race and gender.

For further reading on emotion and literary studies, we recommend:
Kim, Evgeny, and Roman Klinger. ["A Survey on Sentiment and Emotion Analysis for Computational Literary Studies.](https://zfdg.de/2019_008) "ZfdG - Zeitschrift für digitale Geisteswissenschaften, 2018. 


## How Does it Work?
There are two main approaches to sentiment analysis, supervised learning and unsupervised learning
* **Unsupervised** learning (lexical or lexicon-based) methods is when a sentiment of a text is analysed based on the presence of unambiguous affect words such as happy, sad, afraid, bored, angry. 
* **Supervised** learning (statistical or machine learning) “works by feeding the program with examples of positive and negative texts so that the algorithm can learn their typical distinguishing features.”
Thelwall, Mike. “Sentiment Analysis.” The SAGE Handbook of social media research methods, edited by Luke Sloan and Anabel Quan-Haase, SAGE Publications Ltd, 2017, pp 545-554.  


## Limitations and Pitfalls


## Tools and Methods used for Sentiment Analysis
