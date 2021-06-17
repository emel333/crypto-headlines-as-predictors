# crypto-headlines-as-predictors

Completed by: Marvin L. Mills II


#  Context: Understanding Crypto Market Sentiment 

Bitcoin and other cryptocurrencies represent a new asset class in the world, and with the rapid developments in the market investors need reliable methods for understanding the sentiment of others. Sentiment analysis has been leveraged by hedge funds and other institutional investors for the stock market (and beyond) for some time now, and as well, sentiment analysis has been used within the crypto space.

The question for this project centers on publication headlines, the questions being:

Can we predict crypto market price by analyzing and performing machine learning on publication headlines?

A venture capital firm has asked for the beginnings of a sentiment analysis focused predictor to be explored.

<ul>
    <li>Can headlines alone provide any predictive power in the crypto market?</li>
    <li>How does the keyword "Bitcoin" correlate to the price movement of an Altcoin?</li>
    <li>Are there any significant "trigger words" in headlines?</li>
    <li>How can a model for predicting crypto price movement based on sentiment analysis be approached?</li>
</ul>


# Process (& Data Science Tools) Used:


<ul>
    <li>Used the <i>CoinAPI</i> provided by CoinApi, as well as Apipheny (for querying and gathering dataset from CoinAPI) to capture historical Litecoin price data</li>
    <li>With Newsfetch I scraped headlines from 3 of the top crypto publications online using the keyword "Bitcoin"</li>
    <li>Performed NLP using Stopwords (for pre-processing) and NLTK (for Word Frequency)</li>
    <li>Labeled all headlines according to the week in which they were published, and in accordance with weekly Litecoin price data</li>
    <li>Heavy usage of decision tree models (Random Forest, XGBoost) as well as Logistic Regression for modeling</li>
    <li>Focused on precision score so as to minimize the number of False Positives (or, predicting "up" when the truth is "down")</li>
    <li>Gathered feature importances and highest impact words to get initial sense for modeling effectiveness</li>
</ul>


# Findings:


### Balanced Target Variable, With Headlines Corresponding To Both Upward and Downward Price Movement

Of the total number of headlines, there's nearly a 50-50 split for 'upward' and 'downward' Litecoin price movement, even with the keyword searched being "Bitcoin".

![alt text](https://github.com/emel333/time_series_home_prices/blob/main/Graphics/charlotte-and-surrounding-hroi.JPG "Historical ROI Top 21 Zip Codes In Charlotte, NC and Surrounding Areas")


### Logistic Regression Baseline Model Could Not Be Confidently Cast Aside

With a precision score of 0.661 (at the time the model was run), it was the best performing model, however more must be done to optimize the use of models like XGBoost along with GridSearchCV to further compare.

![alt text](https://github.com/emel333/time_series_home_prices/blob/main/Graphics/charlotte-and-surrounding-hroi.JPG "Historical ROI Top 21 Zip Codes In Charlotte, NC and Surrounding Areas")



### The Words "Bitcoin" and "highs" have high feature importance, but differ in terms of impact on upward and downward Litecoin price movement

Even with multiple attempts at modeling, and with varied results in scoring, the top features consistently proved to be the words "Bitcoin" and "highs." However, in terms of significance, the word "high" has proven better than the word "Bitcoin".

![alt text](https://github.com/emel333/time_series_home_prices/blob/main/Graphics/differencing-onelag-28204.JPG "Zip Code 28204: One Difference")
![alt text](https://github.com/emel333/time_series_home_prices/blob/main/Graphics/seasdecom-28204.JPG "Zip Code 28204: After Seasonal Decomposition")



### The most frequent words vs. the most significant words maintain stark contrast

Using NLTK, I created word clouds displaying the most frequent words in all of the headlines that corresponded to upward price movement, and did the same for headlines corresponding to downward price movement. There doesn't appear to be much differentiating these two, however, with respect to feature significance to BOTH upward and downward price movement, other words proved more significant, particularly action verbs have a significant presence in the group of words.


![alt text](https://github.com/emel333/time_series_home_prices/blob/main/Graphics/shorter-series-modeling-sarimax-vis.JPG "SARIMA Model Verification Results: Residuals + Histogram For Series 2010-2018")
![alt text](https://github.com/emel333/time_series_home_prices/blob/main/Graphics/longer-series-modeling-sarimax-vis.JPG "SARIMA Model Verification Results: Residuals + Histogram For Series 1996-2018")
![alt text](https://github.com/emel333/time_series_home_prices/blob/main/Graphics/longer-series-modeling-sarimax-vis.JPG "SARIMA Model Verification Results: Residuals + Histogram For Series 1996-2018")



# Recommendation -- Consider Article Summaries or Meta Descriptions Next

Instead of headlines, it may be worth taking a similar approach but with the summaries or meta descriptions of the articles included here. Moreover, perhaps combining the price movement of multiple digital currencies (i.e. the top 100) could prove useful as well.



# Summary + Further Research:


<ul>
    <li>The words "bitcoin" and "highs" were the top features</li>
    <li>Action verbs have significance presence in the group of words that statistically are most significant to BOTH upward and downward price movement</li>
    <li>Combine the historical price data of multiple currencies to analyze alongside the headlines</li>
    <li>It does appear at least valuable to perform NLP analysis alongside crypto market data, to at the very least understand whether a word is a "trigger" word or indicator for the markets</li>
</ul>