As Professor Mori recommended, besides Elements of Statistis, another book is also great, called "All of Statistics". Now I am reading it when my code is running. Need to take notes for those sattistics details I didn't know. Although I downloaded the free book from school library, it's better to put the book url from Amazon. You can find the book here: https://www.amazon.com/All-Statistics-Statistical-Inference-Springer/dp/1441923225


**************************************************************************************

CHAPTER 11 - Hypothesis Testing and p-values

* H0 is null hypothese, H1 is alternative hypothesis. The goal is to reject H0 or not
* <b>NOTE!</b>: Somtimes testing hypothesiscan be inappropriate
* Type 1 error - reject H0 when H0 is true (like false positive)
* Type 2 error - reject H1 when H1 is true (like false negative)
* one-side test: To test `H0 >= x vs. H1 < x`, or `H0 < x vs. H1 >= x`
* two-side test: To test `H0 == x vs. H1 != x`
* 3 Major Tests
  * Wald Test
  * p-test
  * chi-square distribution
* When using Wald test, testing the hypothesis equivalents to checking whether the null value is in the confidence interval
* p-values - To make it more informative, by not only knowing reject H0 or not, but also knowing at which level reject H0, here comes p-test. This level value is p-value, <b>the smaller the p-value, the stronger evidence against H0</b>
  * p-value < 0.01: very strong evidence against H0
  * 0.01 <= p-value <= 0.05: strong evidence against H0
  * 0.05 < p-value < 0.1: wake evidence against H0
  * p-value >= 0.1: little or no evidence against H0
  * p-value is NOT the probability that the null hypothesis H0 is true
  * If p-value is less than 0.05, then you can report that "the result is statistically significant at 5 percent level". And H0 (null hypothesis) will be rejected only and only if p-value < 0.05
  * NOTE: A result can be statistically significant but the size of effect can be small, which is not practically significantly. Therefore, you need to mention confidence interval too
* Chi-square Distribution
  * Z1, Z2, ... Zk are independent, standard normals. V = power(Z1, 2) + power(Z2, 2) + ... + power(Zk, 2). Then we will say that V has chi-square distribution with k degree of freedom
  * Person's chi-square test is for multinormial distribution
  * P190 has a good example
    * Calculate chi-square value based on observed and expected data first, with both probability and degree of freedom, you can get the reject chi-square, <b>if your calculated chi-square is larger</b> than this value, <b>then reject hypothesis</b>. Use this calculator: http://www.danielsoper.com/statcalc/calculator.aspx?id=12
    * p-value is not chi-square, but you can calculate relative p-value. After you got this value p, use `1-p` to get probability, which could tell you whether it's strong evidence against H0. <b>The smaller the probability is, the stronger the evidence to against H0</b>. Here is the calculator: http://www.danielsoper.com/statcalc/calculator.aspx?id=11
* Permutation Test
  * non-parametric method, to test whether 2 distributions are the same
* Multiple Testing
  * Used when there are so many hypothesis tests need to be done. When there are many pypothesis tests, and each test is using the same reject probability, the probability of false rejection can be very high
  * Assume there is `H0i vs H1i, i = 1,2,...,m`. We use P1, P2, ... Pm to denote the p-value for these tests. 𝛂 is the reject probability for each test.
  * Method 1 - Bonferroni Method
    * Reject H0i `iff Pi < 𝛂/m`
    * When using Bonferroni method, the probability of false rejecting any null hypothesis H0 is less than or equal to 𝛂
    * Bonferroni is a very conservative method, because it is trying to make it unlikely that you would make even one false rejection
  * FDR (False Discovery Rate) = `mean(number of false rejections)/num of rejections`
  * Method 2 - Benjamini-Hochberg(BH) Method
    * There is a BH threshold t
    * Reject all null hypothesis H0i for which Pi <= t
    * `FDR <= m0*𝛂/m <= 𝛂`
    * FDR method controls the fraction of false discoveries, which is a more resonable criterion
