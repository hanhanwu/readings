# Data Science Solutions

When I'm chekcing time series related solutions, sometimes will find stock related learnings. Better to seperate them from my other time series learnings.


## Regime Shift Models - Forecast Regime
* For stock data, the next time period can change dramatically from its previous period, and basic time series models won't work well. "Regime shift models address this gap in basic time series modelling by segregating the time series into different “states”. These models are also widely known as state-space models in time series literature."
* Markov Switching Autoregressive Models assume the regime to be a ‘hidden state’ whose probability and characteristics are estimated using maximum likelihood estimation.
  * Before appliying this solution, the reference suggests to make sure the time series data is stationary
  * Then it applies smoothed marginal probabilities to predict the probability of low/medium/high variance regimes, and that's the regime prediction results...
* [Reference][1]


## [Z Score Ranking based on Returns][2]
* It calculates the z score of returns to rank the top fund. 
* Among funds that get the returns larger than the expected value, it find those with larger differences as the top choices



[1]:https://www.analyticsvidhya.com/blog/2019/10/regime-shift-models-time-series-modeling-financial-markets/?utm_source=feedburner&utm_medium=email&utm_campaign=Feed%3A+AnalyticsVidhya+%28Analytics+Vidhya%29
[2]:https://www.analyticsvidhya.com/blog/2021/03/end-to-end-application-of-data-science-in-personal-finance-mutual-funds-ranking/?utm_source=feedburner&utm_medium=email&utm_campaign=Feed%3A+AnalyticsVidhya+%28Analytics+Vidhya%29
