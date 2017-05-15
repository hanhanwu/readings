The bible is the bible, deserve to read and think again and again! This is the reading notes for my favorite data mining book, written by the father of Data Mining. The book includes not only detailed description & easy-to-understand examples for machine learning algorithms (it even talks about how to improve algorithm efficiency, how to find interesting results for practical use), machine learning methods & pseudo code & Evaluation, but also contains great summary of data warehousing, as well as general summary of data preprocessing methods.


************************************************************************

<b>Chapter 6: Mining Frequent Patterns, Associations, and Correlations: Basic Concepts and Methods</b>

Finding frequent patterns plays an essential role in mining associations, correlations, and many other interesting relationships among data. Moreover, it helps in data classification, clustering, and other data mining tasks. Thus, frequent pattern mining has become an important data mining task and a focused theme in data mining research.

-- BASIC CONCEPTS

* <b>support</b> and <b>confidence</b> are two measures of rule interestingness, thye respectively reflect the <b>usefulness</b> and <b>certainty</b> of discovered rules. For example, a pattern is showing 90% confidence, means high certainty, but only 10% support means it happens rare among all the patterns. <b>Typically, association rules are considered interesting if they satisfy both a minimum support threshold and a minimum confidence threshold.</b>
* `support(A => B)=P(A U B)`, `confidence(A => B) = P(B|A)`, the probabilities here are calculated among all the trainsactions in the database (D). Support s, where s is the percentage of transactions in D that contain A U B; Confidence c in the transaction set D, where c is the percentage of transactions in D containing A that also contain B.
* Rules that satisfy both a minimum support threshold (min_sup) and a minimum confidence threshold (min_conf) are called <b>strong</b>. 
* An itemset that contains k items is a <b>k-itemset</b>. The set {computer, antivirus software} is a 2-itemset.
* <b>frequency/support count/count/occurrence frequency of an itemset</b>, is the number of transactions that contain the itemset. The support mentioned above is `relative support`, while itemset frequency is `absolute support`
* If the relative support of an itemset I satisfies a prespecified minimum support threshold, (i.e., the absolute support of I satisfies the corresponding minimum support count threshold), then I is a <b>frequent itemset</b>.
* `confidence(A => B) = P(B|A) = support(A U B)/support(A) = support_count(A U B)/support_count(A)`
* <b>NOTE</b>: P(A U B) indicates the probability that a transaction contains the union of sets A and B. This should not be confused with P(A or B), which indicates the probability that a transaction contains either A or B.
* <b>If an itemset is frequent, each of its subsets is frequent as well</b>
* To overcome there could be huge amount of items for computation, they introduced <b>closed frequent itemset</b> and <b>maximal frequent itemset</b>.
* X is <b>closed</b> in a data set D if there exists no <b>proper super-itemset Y</b> such that Y has the same support count as X in D. An itemset X is a <b>closed frequent itemset</b> in set D if X is both closed and frequent in D. An itemset X is a <b>maximal frequent itemset/max-itemset</b> in a data set D if X is frequent, and there exists no frequent super-itemset Y.
* <b>NOTE</b>: "proper super-itemset" means Y contains X and Y should has at least 1 item does NOT in X
* The set of closed frequent itemsets contains complete information regarding the frequent itemsets. However, from the maximal frequent itemset, we can only assert some itemsets are frequent, but we cannot assert their actual support counts.
* <b>Apriori</b>
  * Apriori employs an iterative approach known as a level-wise search, where k-itemsets are used to explore (k + 1)-itemsets, until no more frequent itemsets can be found. It is a seminal algorithm for <b>mining frequent itemsets</b> for <b>Boolean association rules</b>.
  * Apriori property: All nonempty subsets of a frequent itemset must also be frequent. The property is <b>antimonotonicity</b> in the sense that if a set cannot pass a test, all of its supersets will fail the same test as well. It is called antimonotonicity because the property is <b>monotonic</b> in the context of failing a test. In Apriori, we use this property for prunning step, using "Any (k-1)-itemset that is not frequent cannot be a subset of a frequent k-itemset.", we remove those un-frequent subsets, in order to reduce computation cost.
  * Join & Prune
  * Nontrivial costs:
    * still may generate hugh amounnt of candidate sets
    * need to repeatedly scan the whole database and check large set of candidates by pattern matching
* Improve the efficiency of Apriori
  * Hash-based technique: hash k-itemsets and their counts, remove those have less than min_sup
  * Transaction reduction: remove transactions directly, when it has j-itemsets is non-frequent, because if the subset cannot frequent, the superset cannot be frequent either (Apriori property)
  * Partitioning: Step 1 - Local scan for each partition, the local min_sup for each partition = global min_sup * number of transactions in that partition; Step 2 - Global scan, with global min_sup
  * Smapling: Use a random sebset for analysis, in case the global frequent itemset could be missed, the min_sup for sample set can be smaller than actual min_sup
  * Dynamic itemset counting: database is partitioned into blocks marked by start points, new candidate itemsets can be added at any start point. Unlike in Apriori, which determines new candidate itemsets only immediately before each complete database scan. If the count-so-far passes the minimum support, the itemset is added into the frequent itemset collection and can be used to generate longer candidates
* FP-growth (frequent pattern growth)
  * To deal with the 2 nontrivial costs of Apriori, FP-growth has been created, it may substantially reduce the size of the data sets to be searched, along with the “growth” of patterns being examined
  * Firstly, it compresses the database representing frequent items into a frequent pattern tree, or FP-tree, which retains item association; The the problem became mining the FP-tree, it  divides the compressed database into a set of conditional databases, each associated with one frequent item or “pattern fragment,” and mines each database separately. For each “pattern fragment,” only its associated data sets need to be examined.
  * <b>When the database is large, it is sometimes unrealistic to construct a main memory- based FP-tree. An interesting alternative is to first partition the database into a set of projected databases, and then construct an FP-tree and mine it in each projected database. </b>
  * FP-growth is efficient and scalable for mining both long and short frequent patterns, and is about an order of magnitude faster than the Apriori algorithm.
* H-Mine (it's even better than FP-growth)
  * The paper: https://www.cs.sfu.ca/~jpei/publications/hmine.pdf
  * Professor's PPT (only after school graduation, suddenly realized his class is in fact a very good one....): http://www.cs.sfu.ca/CourseCentral/741/jpei/
  * Advantages:
    * It has very limited and precisely predictable space overhead and runs really fast in memory-based setting
    * Absorbs nice features of FP-growth, but creats no physical projected database. Watches the density of projected databases, turn to FP-growth when necessary
    * Scalable in very large database and feasible even with very small memory
* <b>horizontal data format</b>: {TID : itemset}
* <b>vertical data format </b>: {item: TIDset}
* Eclat (Equivalence Class Transformation)
  * While both Apriori and FP-growth are using horizontal data format, Eclat is using vertical data format
  * it takes advantage of the Apriori property in the generation of candidate (k + 1)-itemset from frequent k-itemsets, and there is no need to scan the database to find the support of (k + 1)-itemsets since TID set of each k-itemset carries the complete information required for counting such support. 
  * However, the TID sets can be quite long, taking substantial memory space as well as computation time for intersecting the long sets. Use `diffset (k-itemset, k+1-itemset)` to record the difference.
  * When the data set contains <b>many dense and long patterns</b>, this technique can substantially reduce the total cost of vertical format mining of frequent itemsets.
* Mining Closed & Max Patterns
  * Closed frequent itemsets can substantially reduce the number of patterns generated in frequent itemset mining while preserving the complete information regarding the set of frequent itemsets. Therefore, it is more desirable to mine the set of closed frequent itemsets rather than the set of all frequent itemsets in most cases.
  * I am unserdtanding it in this way, it works similar to FP-tree but repalces frequent itemset with closed frequent itemset/maximal frequent itemset. (It also has other design to make the algorithms more efficient)
  * e.g. MaxMiner, CLOSET, CHARM
* For many implemented algorithms related to Pattern Mining, I dind't find enough in R or spark or Scikit-Learn, however, I found SPMF, it's Jave, but it really has lots of relative implemented algorithms:
  * SPMF Algorithms: http://www.philippe-fournier-viger.com/spmf/index.php?link=algorithms.php
  * SPMF examples: http://www.philippe-fournier-viger.com/spmf/index.php?link=documentation.php
  * SPMF algorithm mapping: http://www.philippe-fournier-viger.com/spmf/map_algorithms_spmf_data_mining097.png
