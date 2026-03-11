from textblob import TextBlob
import pandas as pd

dataset = dataset.copy()

def get_sentiment(text):
    polarity = TextBlob(text).sentiment.polarity
    
    if polarity > 0:
        return "Positive"
    elif polarity < 0:
        return "Negative"
    else:
        return "Neutral"

dataset['Sentiment'] = dataset['ReviewText'].apply(get_sentiment)

result = dataset
