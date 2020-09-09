# Learning Trading Systems 🌺

I'm learning this book [Trading Systems and Methods][1], and already started to feel excited about the new knowledge. Taking some learning notes here for my future use! 💖

## [Terminology & Usage][7]
* Having all the terminology in 1 chapter of an e-book is such a torture, but have to take notes so that later it's easier to check again.


## Suggestions
* None of these are the only factor for decison making.

### About Noise
* Checking the noise helps decide which market to trade and whether to enter a market quickly or wait a bit.
  * <b>A trend system can be more profitable when the price series has less noise, and a mean reversion strategy is better when there is more noise.</b>
  * To measure the noise, we can often use `efficiency ratio`
    * `efficiency_ratio = abs(Pt - Pt-n) / sum(abs(Pi - Pi-1)), i = t-n ... t`
      * "P" means price here, "Pi" means the price at time i
      
### About Data Collection
* More data more situations
  * large amount of data can be more reliable
  * Better to include both bull and bear markets, occasional large price shork, etc.
  * Older data doens't mean irrelevant
* Better to focus on data from US or Europe, other data sources can be late or less accurate
* Having both training and testing data

### Metrics
#### Error Measurement
* `sample error = 1/sqrt(N)`, N is the data size.
  * It helps tell how much data do you need to achieve enough accuracy
  * To achieve around 5% error, it needs 400 trades
* `standard error = SE = sqrt(var/n)`, n is sample size
  * It uses multiple data samples to estimate the data distribution. The value determines how the sample means differ from the actual mean. -- The uniformity of data
  * People also use all the data with size N, instead of multiple samples


## New Feeds
* [Bloomberg][2]
  * I tried to find US but only has Canada...
* [Reuters][3]

## Tools
* [TradeStation][4]
* [MetaStock][5]
* [NinjaTrader][6]

[1]:https://www.amazon.ca/Trading-Systems-Methods-Perry-Kaufman/dp/1119605350/ref=asc_df_1119605350/?tag=googleshopc0c-20&linkCode=df0&hvadid=378366144916&hvpos=&hvnetw=g&hvrand=7537460615457728344&hvpone=&hvptwo=&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=9001506&hvtargid=pla-834172661206&psc=1
[2]:https://www.bloomberg.com/canada
[3]:https://www.reuters.com/news/us
[4]:https://www.tradestation.com/
[5]:https://www.metastock.com/
[6]:https://ninjatrader.com/
[7]:https://github.com/hanhanwu/readings/blob/master/Trading_Systems/build_common_sense.md
