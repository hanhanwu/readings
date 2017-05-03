So, finally I can spend more time to study this book, I have heard that it's a great statistics book for machine learning. Here, I am recodring the notes when I am reading. I am also marking on the book and will post the marked book after finish the whole book :)

NOTE: It's better to read Data Mining bible and this book together, and read the bible first since it contains more specific examples: http://www.kvimis.co.in/sites/kvimis.co.in/files/ebook_attachments/Jiawei%20Han,%20Micheline%20Kamber,%20ian%20Pei%20Data%20Mining%203%20ed.pdf


*************************************************************************

CHAPTER 14 - UNSUPERVISED LEARNING

* Association Rules
  * Apriori Alg
    * Requires only one pass over the data for each value of |K|, since it assumes the data cannot be fitted into a computer’s main memory. Therefore, it allows this analysis to be applied to huge data bases
    * The goal of this analysis is to produce association rules (14.7) with both high values of support and confidence. However, rules with high confidence or lift, but low support, will not be discovered, because the number of solution item sets, their size, and the number of passes required over the data can grow exponentially with decreasing size of this lower bound.
    * Apriori algorithm is exhaustive—it finds all rules with support greater than a specified amount.
  * Monte Carlo method: https://en.wikipedia.org/wiki/Monte_Carlo_method
    * Monte Carlo methods (or Monte Carlo experiments) are a broad class of computational algorithms that rely on repeated random sampling to obtain numerical results. Their essential idea is using randomness to solve problems that might be deterministic in principle.
  * Reference to the uniform distribution can cause highly frequent item sets with low associations among their constituents to dominate the collection of highest support item sets.
  * Supervised learning approach, coupled with <b>a ruled induction method</b> such as CART or PRIM, can uncover item sets exhibiting high associations among their constituents. For example, PRIM also produces rules precisely of the form, but it is especially designed for finding high-support regions that maximize the average target.
  * While Apriori is axhausive, PRIM is a greedy algorithm (local optimal in each step) and is not guaranteed to give an “optimal” set of rules. However, Apriori algorithm can deal only with dummy variables, may not find the rules can be found through PRIM
