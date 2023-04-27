import tweepy
from textblob import TextBlob

# Autenticación en Twitter API
consumer_key = 'YOUR_CONSUMER_KEY'
consumer_secret = 'YOUR_CONSUMER_SECRET'
access_token = 'YOUR_ACCESS_TOKEN'
access_token_secret = 'YOUR_ACCESS_TOKEN_SECRET'

auth = tweepy.OAuthHandler(consumer_key, consumer_secret)
auth.set_access_token(access_token, access_token_secret)

# Crear objeto API
api = tweepy.API(auth)

# Búsqueda de tweets y análisis de sentimiento
public_tweets = api.search('apple')
for tweet in public_tweets:
    analysis = TextBlob(tweet.text)
    print(tweet.text)
    print(analysis.sentiment)
