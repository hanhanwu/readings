# Build Common Sense

## Usage
### Calculate the probability of a return
* `probability of reaching objective = (objective - mean)/std`
* For example, you have the distribution of the returns in a certain period, knowing the mean 8% and std 16%, and you want to reach 20+% return, the probability will be (20% - 8%)/16%
### Usage of t-test
* Measure how close the sample distribution is to normal distribution
  * `t = (mean - population mean) * sqrt(sample_size)/sample_std`
* Compare 2 periods data, to see whether there is significant change
  * When calculating the consistency of profits & losses of a trading system, mean and std values are trading returns, sample size is using the number of trades
* For more, check [my past notes][1]

## Terminology
* `equilibrium` -  the supply and the demand are balanced
* `Serial Correlation` or `autocorrealtion`, it looks for the persistence in the data
  * Use d-test, Durbin-Watson test, it measures the changes in errors. The value of d is between 0..4 range
    * There is no correlation when d = 2
    * Less than 2 there us positive autocorrelation (more similarity), but when it's below 1, there is more similarity in the errors than is reasonable
    * Above 2, the more negative autocorrelation appears in the error terms
* Calculate returns
  * `standard return = r_t = (Equity_t - Equity_t-1)/Equity_t-1`
  * `ln return = r_t = ln(Equity_t/Equity_t-1)`
  * Net Asset Values (NAVs), `NAV_t = NAV_t-1 * (1 + r_t)`, it often has a starting value NAV_0
  * Trading returns are best with 252 days, the typical number of days in a trading year in US
  * Annualized Rate of Return (AROR)
    * `AROR_compounded = power(E_n/E_0, 252/n) - 1`, over n days
      * E_0 is the satrting equity or account balance; E_n is the equity at the end of n days

### The law of averages
* It means, the number of average items is extremely large that small abnormal events do not affect the balance.
* A long term of profits, losses or an abnormal event will be offset over time by the overwelmingly number of normal events.
* `weighted average = (a1d1 + a2d2 + ... andn)/(d1 + d2 + ... + dn)`
  * `ai` is the average price during the time interval; `di` is the total days during the time interval
  * having the number of days as the weight here helps tell the average price in a more accurate way
* `geometric mean = G = (a1 * a2 * .... * an)^(1/n)`, or `(ln(G) = (ln(a1) + ln(a2) + ... + ln(an))/n)`
  * `a1 .. an-1` are the smallest price of each interval, `an` is the largest price of the last interval; `n` is the number of time intervals
  * natural log here
  * This mean helps measure the price growth, it's important when using data represent precentages, ratios or rates of changes.
* `quadratic mean = sqrt(sum(power(ai))/N)`
  * It often used to estimate errors
* `harmonic mean = H = n/sum(1/ai)`
  * Similar to geometric mean, `a1 .. an-1` are the smallest price of each interval, `an` is the largest price of the last interval; `n` is the number of time intervals
* `arithmetic mean > geometric mean > harmonic mean` when the distribution is not perfectly symmetric
  * "arithmetic mean" here is the weighted average with equal weight
  
### Distribution
* 4 moments of distribution
  * mean, variance, skewness, kurtosis
    * Kurtosis measures the peakness of the distribution. For a more flatten distribution, it's negative kurtosis; for a more peaked distribution, it's positive kertosis.
      * <b>The kurtosis of the daily returns will be better than 3 if the system is profitable.</b>
        * The normal value of kurtosis is 3
        
### Index
* It's used to convert markets calculated in different units into the same metric, so that they are comparable
#### Index Categories
* Capitalization Weighted (market-value-weighted index)
  * `outstanding shares * price`
  * Such as S&P 500, NASDAQ 100, the Hang Seng, the MSCI EAFE Index, the German DAX, the Japanese TOPIX
* Price Weighted
  * `average price of all components`
  * Such as Dow Jones Industrials, the Nikkei 225
* World Production Index
  * More production is more important to the index
  * Such as GSCI (Goldman Sachs Commodity Index), it's weighted by the production of the component commedities over the past 5 years
* Trade Weighted Index
  * Such as US Dollar Index
    * It's trade weighted, a geometric average of 6 currencies: 57.6% euro; 13.6% Japanese yen; 11.9% UK pound; 9.1% Canadian dollar; 4.2% Swedish krona and 3.6% Swiss franc.
    * The dollar index increases in value relative to the other currencies.
* Commodity Index Market
  * The index has specific weightetings for different commodities (such as 30.57% energy, 23.46% grains, 17.39% industrial metals, 15.29% precious metals, etc.)
  * Such as BCI (bloomberg commodity index), DJ-UBS, CRB(Commodity Research Bureau Index), Thomson Reuters Equal Weight Continuous Commodity Index (a simple average of the daily price of the 17 components)
* Price-Volume Index
  * Not popular, used to reflect the strength of move. `price * volume`

## Common Sense
* Wheat prices can also be viewed net of inflation or changes in US dollar


[1]:https://github.com/hanhanwu/Hanhan_Data_Science_Practice/blob/master/Applied_Statistics/pvalue_ttest_ztest.md
