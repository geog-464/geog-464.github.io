# What is an API?

- API is an acronym that stands for *Application Programming Interface.*
- An API is a set of protocols and tools that allow software applications to communicate with each other (often over the web, but not always). An API allows a system to request access to data or services of another system through a set of clearly defined methods.

To break it down:
- **Application**: Any algorithm / piece of software / program with a distinct function
- **Programming**: Access is predefined and can be reached programmatically via the...
- **Interface**: The interface can be thought of as a series of cafeteria counters which we call *endpoints*: points of entry to access the functionality of any given system. These points of entry usually involve transactions which contain parameters that help define the kind of information or service being requested. Such interactions involve a "[contract of service](https://aws.amazon.com/what-is/api/)" between two applications (what you ask for and what you get in return), defined in the API's documentation.

Simply put, an API is a set of defined entryways into an application / package / service / data stream.
- An API call can be as simple as a query or function call:
	- A URL defines the endpoint of a Web API 
	- whereas a function call and its arguments may define access to a software library

In all cases, *APIs allow developers to save time by taking advantage of a platform’s implementation to do the nitty-gritty work. This helps reduce the amount of code developers need to create, and also helps create more consistency across apps for the same platform.* 

*All web services are APIs but not all APIs are web services.* - [AWS](https://aws.amazon.com/what-is/api/)

We often think of APIs in the context of the web (a REST API is simply a web API that defines HTTP requests), but you can also refer to certain classes within python packages as APIs (such as the PyPlot API, which provides a high-level way of accessing Matplotlib functionality).

Examples:
- The software system of the weather bureau holds daily weather information. The weather application on your phone communicates with this system through APIs, displaying daily weather updates on your device.
- Using the PyPlot API to access Matplotlib functionality
	- [PyPlot](https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.plot.html) is a module in the matplotlib package that provides a high-level interface for creating plots and charts. It can be considered an API because it provides a set of functions and methods that can be called by the user to generate and customize plots.
```python
import matplotlib.pyplot as plt

plt.plot([1, 2, 3, 4], [1, 4, 9, 16])
```
[src](https://matplotlib.org/stable/tutorials/introductory/pyplot.html#intro-to-pyplot)
- Programmatically accessing tweets via [Twitter's API](https://developer.twitter.com/en/docs/twitter-api), facilitated by a package such as *[Tweepy](https://github.com/tweepy/tweepy)*:
```python
import tweepy

auth = tweepy.OAuth1UserHandler(
   consumer_key, consumer_secret, access_token, access_token_secret
)

api = tweepy.API(auth)

public_tweets = api.home_timeline()
for tweet in public_tweets:
    print(tweet.text)
```
