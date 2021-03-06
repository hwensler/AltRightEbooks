# altright_ebooks

This is based on a port of harrisj's ruby ebooks script and  tommeagher's python implementation.


## Setup

1. Clone this repo
2. Make sure you have [python-twitter] installed. You can find it here: https://github.com/bear/python-twitter
3. Create a Twitter account that you will post to.
4. Sign into https://dev.twitter.com/apps with the same login and create an application. Make sure that your application has read and write permissions to make POST requests.
5. Edit local_settings_example, filling it out completely and changing the name to local_settings.py - you can find all keys from the twitter application you created above. 
6. Take the consumer key (and secret) and access token (and secret) from your Twiter application and paste them into the appropriate spots in `local_settings.py`.
7. Run on AWS.

## Configuring

How to adjust behavior of the bot 

```
ODDS = 8
```
This is the chance that your tweet will actually post. If ODDS = 1, a tweet will post every time. If it is 6, each tweet will have a 1/6 chance of posting. This helps the bot run in a pseudorandom fashion. This is done in 'guess = random.choice(range(ODDS);


By default, the bot ignores any tweets with URLs in them because those might just be headlines for articles and not text you've written.

```
ORDER = 2
```

This is the Markov index, which essentially measures the associativity in the Markov chains generated by this program using the source twitters. Put a number 2-4, where 2 is closer to nonsense and 4 is closer to a lucid human being. 


## Debugging

```
DEBUG = True 
```

If DEBUG = True, this won't actually post to twitter. It's to generate sample tweets locally after tweeking settings.

If you want to avoid hitting the twitter API, you can use a static text file to generate tweets. This txt file should be a python list of quote-wrapped tweets. Set STATIC_TEST to True. Set the file location as the variable equal to TEST_SOURCE.

This is all in local_settings.py


## Credit
As I said, this is based almost entirely on [@harrisj's](https://twitter.com/harrisj) [iron_ebooks](https://github.com/harrisj/iron_ebooks/). He created it in Ruby, and I wanted to port it to Python. All the credit goes to him. It was first implemented in python by tommeagher (https://github.com/tommeagher/heroku_ebooks)
