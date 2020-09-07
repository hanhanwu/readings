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

## Common Sense
* Wheat prices can also be viewed net of inflation or changes in US dollar


[1]:https://github.com/hanhanwu/Hanhan_Data_Science_Practice/blob/master/Applied_Statistics/pvalue_ttest_ztest.md
