Outlier Detection becomes a big chanllenge when it comes to temporal data. This book is talking about outlier detection techniques we can try when it comes to temporary data.
To understand this book, you have to be fully focused, otherwise it is difficult to understand how those algorithms work... The book is a brief summary of different techniques, but in fact, it is interesting to see how those papers come up with creative solutions, without reading them.


********************************************************************

Outliers in TIME SERIES DATABASE

1. Direct Detection of Outliers Time Series
* Given: All database of time series
* Find: All anomalies time series
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
  * Supervised Approaches
    * yeah, no matter how cool the model is, at least you have the ground truth

<b>busy, TO BE CONTINUED.....</b>



