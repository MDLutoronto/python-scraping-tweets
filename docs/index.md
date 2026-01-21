---
title: "Scraping tweets using Python"
layout: "home"
description: ""
permalink: "/"  #! Remove this if not the homepage
---

# Scraping tweets using Python

 

This tutorial demonstrates how to scrape tweets for data analysis using Python and the Twitter API.

Scraping tweets using Python
============================

 **Table of Content**

* [Introduction](https://mdl.library.utoronto.ca/technology/tutorials/scraping-tweets-using-python#intro)
* [The Twitter API](https://mdl.library.utoronto.ca/technology/tutorials/scraping-tweets-using-python#twitter-api)
* [Python environment](https://mdl.library.utoronto.ca/technology/tutorials/scraping-tweets-using-python#python-env)
* [Unicode strings](https://mdl.library.utoronto.ca/technology/tutorials/scraping-tweets-using-python#unicode)
* [oauth2 library](https://mdl.library.utoronto.ca/technology/tutorials/scraping-tweets-using-python#oauth2)
* [Get Twitter data](https://mdl.library.utoronto.ca/technology/tutorials/scraping-tweets-using-python#get-twitter-data)

 

**Introduction**

Twitter is a popular online social network where users can send and read short messages called "tweets." It is also an instrument to measure social events, and each day millions of people tweet to express their opinions across any topic imaginable. This data source is valuable for both research and business.

Here are a few examples of analyzing Twitter data to get some interesting results:

* "Mood" of communication on twitter [reflects biological rhythms](http://www.nytimes.com/2011/09/30/science/30twitter.html)
* Researchers use twitter to [predict the stock market](http://arxiv.org/pdf/1010.3003&embedded=true)
* A student used geocoded tweets to [plot a map of locations where "thunder" was mentioned in the context of a storm system in Summer 2012](http://cliffmass.blogspot.ca/2012/07/thunderstorm-fest.html)
* Characteristics and dynamics of Twitter [have an excellent resource](http://www.ccs.neu.edu/home/amislove/twittermood/) for learning more about how Twitter can be used to analyze moods at national scale

In this tutorial, we will introduce how to use Python to scrape live tweets from Twitter.

 

**The Twitter Application Programming Interface (API)**

Twitter provides a very rich [REST](http://en.wikipedia.org/wiki/Representational_state_transfer) API for querying the system, accessing data, and controling your account. You can [read more about the Twitter API](https://dev.twitter.com/overview/documentation)

 

**Python environment**

If you are new to Python, you may find these resources valuable:

* [Codeacademy's Python tutorials](https://www.codecademy.com/catalog/language/python)
* [Google's Python class](https://developers.google.com/edu/python/)
* [Cleaning data in Python tutorial](https://mdl.library.utoronto.ca/technology/tutorials/cleaning-data-python)

You can install Python by downloading it from the [Python website](https://www.python.org/downloads/). We recommend the Anaconda Scientific Python Distribution \- it is completely free, and ideal for processing data and doing predictive analysis and scientific computing. You can get the latest the version of Anaconda at<http://continuum.io/downloads>. For more information please refer to "Set up enviroments" section in the [Cleaning data in Python tutoral](https://mdl.library.utoronto.ca/technology/tutorials/cleaning-data-python).

 

**Unicode strings**

Strings in the twitter data prefixed with the letter "u" are [unicode](http://en.wikipedia.org/wiki/Unicode) strings. For example:

```

u"I am a string!"
```
Unicode is a standard for representing a much larger variety of characters beyond the roman alphabet (greek, russian, mathematical symbols, logograms from non\-phonetic writing systems such as kanji, etc.)

In most circumstances, you will be able to use a unicode object just like a string.If you encounter an error involving printing unicode, you can use the[encode](http://docs.python.org/2/library/stdtypes.html#str.encode)method to properly print the international characters, like this:

```

unicode_string = u"aaaÃ Ã§Ã§Ã§Ã±Ã±Ã±"
encoded_string = unicode_string.encode('utf-8')
print encoded_string
```
 

**oauth2 library**

To get access the live stream tweets, you will need to install the [oauth2 library](https://pypi.python.org/pypi/oauth2/) so you can properly authenticate. You can install it yourself in your Python environment. (Go to command line and type *pip install oauth2:* it should work for most environments.)

![]({{ '/assets/images/01_0.PNG' | relative_url }})

 

**Get Twitter data**

The steps below will help you set up your twitter account to be able to access live stream tweets.

* Create a [Twitter](https://twitter.com/) account if you do not have one.
* Go to<https://dev.twitter.com/apps>and log in with your Twitter credentials.
* Click "Create New App"
* Fill out the form and agree to the terms. Put in a dummy website if you don't have one you want to use.
* On the next page, click the "Keys and Access Tokens" tab along the top, then scroll all the way down until you see the section "Your Access Token"
* Click the button "Create My Access Token". You can[Read more about Oauth authorization.](https://developer.twitter.com/en/docs/basics/authentication/api-reference/authorize)
* You will now copy your unique four values into [twitterstream.py](https://raw.githubusercontent.com/uwescience/datasci_course_materials/master/assignment1/twitterstream.py) (download this file on your computer). These values are your "**API Key**", your "**API secret**", your "**Access token**", and your "**Access token secret**". Open twitterstream.py and set the variables corresponding to the api key, api secret, access token, and access secret. You will see code like the below in line 6\-9 of the file:

```

api_key = "<Enter api key>"
api_secret = "<Enter api secret>"
access_token_key = "<Enter your access token key here>"
access_token_secret = "<Enter your access token secret here>"
```
* After pasting the four credentials into the twitterstream.py, save the file and go to command line and type: *python twitterstream.py \> tweets.tx*t. Make sure you are in the directory where the file twittersteam.py is saved.

![]({{ '/assets/images/02_0.PNG' | relative_url }})

 

You will see that a tweets.txt file has been created by the system (smilar to one below). This is the file where raw tweet data will be stored.

![]({{ '/assets/images/03_0.PNG' | relative_url }})

* Wait 3\-5 minutes before you stop the program using Crtl\-C in command line. Open the tweets file and you'll see some raw tweets similar to this:

![]({{ '/assets/images/04_0.PNG' | relative_url }})

 

Congratulations! You just scaped some live tweets using Python. Our next tutorial will introduce how to extract useful information from these tweets. Stay tuned!

 

**Acknowledgement:** this tutorial partially builds on the first assignment of[*Introduction to Data Science*](http://www.coursera.org/course/datasci)on Coursera.

Technique: [Extracting data](/technique/extracting-data) \| Tools: [Python](/tools/python)**Date Created:** 2017\-05\-05**Updated:** 2019\-10\-10
