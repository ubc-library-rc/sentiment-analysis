---
 layout: default
 title: Activity - Running a script and reading results
 parent: Outline
 nav_order: 17
---
# Activity: Running a script and reading results

This activity is adapted Zoë Wilkinson Saldaña, "Sentiment Analysis for Exploratory Data Analysis," The Programming Historian 7 (2018), https://doi.org/10.46430/phen0079.

## What is VADER?
VADER, or [Valence Aware Dictionary for Sentiment Reasoning](https://pypi.org/project/vaderSentiment/), is an open-source model used for sentiment analysis. It can detect both polarity (positive / negative) and intensity of a sentiment. It is specifically attuned to sentiments expressed in social media, and works well on texts from other domains.

If you have not had a chance to install Anaconda and set up your environment, you can follow along by making a copy of <a href="https://colab.research.google.com/drive/1TEfYVKE5kriZu3r94x8owY8KRE6-L5am?usp=sharing">this Collab notebook</a>.

# Getting Started
For this activity we'll be making a file.

To use VADER we need to import the SentimentIntensityAnalyzer module into our workspace. The way we do this is by calling on what we've already set up when we installed nltk and asking it to import an additional

Input
{: .label .label-green}
~~~
from nltk.sentiment.vader import SentimentIntensityAnalyzer
~~~

Next, we initialise VADER so we can use it within our Python script
Input
{: .label .label-green}
~~~
sid = SentimentIntensityAnalyzer()
~~~

The variable 'text' now contains the text we will analyse. We'll start with a famous tweet from that <a href="https://twitter.com/MarsPhoenix/status/839088619?s=20">Mars Phoneix rover when it found ice on Mars in 2008.

Input
{: .label .label-green}
~~~
message_text = '''Are you ready to celebrate?  Well, get ready: We have ICE!!!!! Yes, ICE, *WATER ICE* on Mars!  w00t!!!  Best day ever!!'''

print(message_text)
~~~

Now that we have VADER initialised and a message text to work with we can call on the polarity_scores method. This will read the message, process it, and output a dictionary with negative, neutral, positive, and compound scores for the input text.

Input
{: .label .label-green}
~~~
scores = sid.polarity_scores(message_text)
~~~

Finally we can loop through the keys contained in scores (pos, neu, neg, and compound scores) and print the key-value pairs as well

Input
{: .label .label-green}
~~~
for key in sorted(scores):
        print('{0}: {1}, '.format(key, scores[key]), end='')
~~~

### Putting it all together

You can save all of these steps as a script by creating a .py file in a text editor such as nano from the terminal.

Input
{: .label .label-green}
~~~
nano touch myscript.py
~~~

Copy paste the following:

Input
{: .label .label-green}
~~~
from nltk.sentiment.vader import SentimentIntensityAnalyzer

sid = SentimentIntensityAnalyzer()

text = '''Are you ready to celebrate?  Well, get ready: We have ICE!!!!! Yes, ICE, *WATER ICE* on Mars!  w00t!!!  Best day ever!!'''

print(text)

scores = sid.polarity_scores(text)

for key in sorted(scores):
        print('{0}: {1}, '.format(key, scores[key]), end='')
~~~

Enter **ESC** and select **Y** for yes when prompted. Your file is now saved in the location you were in when you created it. You can double check by listing the files in your current location:

Input
{: .label .label-green}
~~~
ls
~~~

Now we can try running the script!

Input
{: .label .label-green}
~~~
python myscript.py
~~~

Try changing the text by removing some of the exclamation marks and rerunning the script -- what happens?
{: .note}

The output should give you a polarity score for the text in the terminal. You can also print the output to a text file.

Input
{: .label .label-green}
~~~
python myscript.py > output.txt
~~~

# Next Steps

Let's look at how we might use this with a larger block of text. For instance, a paragraph. Below is the same script but with sentence-level analysis.

To look at the sentences in a paragraph we need to tokenize the text and we do this by importing a new module.
~~~
from nltk import word_tokenize
~~~

We use the "english.pickle" function from punkt to give it a short name.
~~~
tokenizer = nltk.data.load('tokenizers/punkt/english.pickle')
~~~

Our text is coming from <a href="https://www.nasa.gov/home/hqnews/2008/jul/HQ_08_195_Phoenix_water.html">NASA's official statement</a> on the Phoenix Rover finding ICE.

~~~
text = '''Laboratory tests aboard NASA's Phoenix Mars Lander have identified water in a soil sample. The lander's robotic arm delivered the sample Wednesday to an instrument that identifies vapors produced by the heating of samples.

"We have water," said William Boynton of the University of Arizona, lead scientist for the Thermal and Evolved-Gas Analyzer, or TEGA. "We've seen evidence for this water ice before in observations by the Mars Odyssey orbiter and in disappearing chunks observed by Phoenix last month, but this is the first time Martian water has been touched and tasted."
'''
~~~

We break up the text by using our new tokenizer function which uses "english.pickle" function from punkt to split text into sentences. It's not perfect and sometimes gets confused by spacing.
~~~
sentences = tokenizer.tokenize(message_text)
~~~

Finally, we need to move through all of the sentences, not just one, and use a for loop to do so.
~~~
for sentence in sentences:
        print(sentence)
        scores = sid.polarity_scores(sentence)
        for key in sorted(scores):
                print('{0}: {1}, '.format(key, scores[key]), end='')
        print()
~~~

Input
{: .label .label-green}
~~~
nano touch sentence.py
~~~

Copy over this new script.

Input
{: .label .label-green}
~~~
import nltk.data
from nltk.sentiment.vader import SentimentIntensityAnalyzer
from nltk import sentiment
from nltk import word_tokenize

sid = SentimentIntensityAnalyzer()

tokenizer = nltk.data.load('tokenizers/punkt/english.pickle')

text = '''Laboratory tests aboard NASA's Phoenix Mars Lander have identified water in a soil sample. The lander's robotic arm delivered the sample Wednesday to an instrument that identifies vapors produced by the heating of samples.

"We have water," said William Boynton of the University of Arizona, lead scientist for the Thermal and Evolved-Gas Analyzer, or TEGA. "We've seen evidence for this water ice before in observations by the Mars Odyssey orbiter and in disappearing chunks observed by Phoenix last month, but this is the first time Martian water has been touched and tasted."
'''

sentences = tokenizer.tokenize(text)

for sentence in sentences:
        print(sentence)
        scores = sid.polarity_scores(sentence)
        for key in sorted(scores):
                print('{0}: {1}, '.format(key, scores[key]), end='')
        print()
~~~

Again enter **ESC** and select **Y** for yes when prompted. Your file is now saved in the location you were in when you created it.

Run the script as before.

Input
{: .label .label-green}
~~~
python sentence.py
~~~
