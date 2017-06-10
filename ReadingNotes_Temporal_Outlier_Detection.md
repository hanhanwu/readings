Outlier Detection becomes a big chanllenge when it comes to temporal data. This book is talking about outlier detection techniques we can try when it comes to temporary data.
To understand this book, you have to be fully focused, otherwise it is difficult to understand how those algorithms work... The book is a brief summary of different techniques, but in fact, it is interesting to see how those papers come up with creative solutions, without reading them.

I'm taking notes majorly when my big data code is running...
********************************************************************

Outliers in TIME SERIES DATABASE

1. Direct Detection of Outliers Time Series
* <b>Given</b>: All database of time series
* <b>Find</b>: All anomalies time series
* Assumption: Most of the data are normal, only a few are anomalous
  * Unsupervised Discriminative Approaches
    * Measure the similarity between 2 sequences
    * Cluster sequences to maximize within-cluster similarity and minimize between cluster similarity
  * Unsupervised Parametric Approaches
    * Without any labeled data, asummarized model will be built based on the data, then a new sequence can be marked as anomalous if the probability for the model to generate the sequence is low
  * Unsupervised OLAP-based Approches
    * A time series could contain a set of time series, each with multi-dimensional features
    * Use OLAP cube, and the time series could associate with each cell
    * A cell will expect the descendent cell (subset) to follow similar evolutionary behaviour, so a descendent cell will be considered as anomalious, if the trend, magnitude or phase of the time series it associates with will significantly differ from the expected value
  * Supervised Approaches <b>[supervised]</b>
    * yeah, no matter how cool the model is, at least you have the ground truth
 
2. Window-based Detection of Outlier Time Series
* <b>Given</b>: All database of time series
* <b>Find</b>: All anomalous time windows
* A test sequence will be broken into <b>multiple overlap subsequences (windows)</b>, the anomaly score is computed for each window, and then calculate the overall anomaly score for the entire test sequence, based on each window score
* This method could better locate anomalies, compared to the above methods which output the entire time series as anomalies
* In differenr scenarios, windows can be called as: fingerprints, pattern fragments, detectors, sliding windows, motifs, n-grams
  * Normal Pattern Database Approach <b>[supervised]</b>
    * First of all, you have already known what are the normal sequences
    * Divide normal sequences into w overlapping windows, each window is stored with its frequency
    * When a new test sequence comes, divide it into w windows, if a window never appeears in stored normal sequences, consider as a mismatch, if a test sequence has large amount of mismatch, mark it as anomaly
    * Match methods can be soft
    * Windows can be continuous, or lookahead-based (record the elements at distance 1,2,...k of a sequence)
  * Negative amd Mixed Pattern Database Approaches
    * This is an improvement of Normal Pattern Database Approach
    * While marking anomalies, you also have a dictionafry to record these anomalies, when a new window comes and matches the anomaliy, consider it as anomaly
    
3. Outlier Subsequences in A Test Time Series
* <b>Given</b>: All database of time series D and a test time series t
* <b>Find</b>: All outlier subsequence/pattern p in t
* Anomaly score is computed as the difference between observed frequency of p and the expected frequency fo p
* The methods to match p can be soft and efficient

4. Outlier Points Across Multiple Time Series
* <b>Given</b>: All database of time series D
* <b>Find</b>: An outlier point across a set of time series

<b>Many other work need to do, TO BE CONTINUED.....</b>



