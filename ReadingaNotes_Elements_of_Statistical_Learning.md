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

* Clustering
  * Specifying an appropriate dissimilarity measure is far more important in obtaining success with clustering than choice of clustering algorithm.
  * Measure Dissimilarity
    * Quantitative variables - squared-error loss (xi − xi′)^2, and absolute error, The former places more emphasis on larger differ- ences than smaller ones. Clustering based on correlation(similarity) is equivalent to that based on squared distance (dissimilarity)
    * Ordinal variables (ordered contiguous integers) - Error measures for ordinal variables are generally defined by replacing their M original values with (i-0.5)/M, i=1,...,M
    * Categorical variables - A variable assumes M distinct values, these can be arranged in a symmetric M × M matrix
  * Clustering Modle Types
    * Combinatorial algorithms - work directly on the observed data with no direct reference to an underlying probability model. Each observation is assigned to one and only one cluster. Each individual cluster assignments for each of the N observations to minimize a “loss” function. These algorithms converge to local optima which may be highly suboptimal when compared to the global optimum.
    * Mixture modeling - supposes that the data is an i.i.d sample from some population described by a <b>probability density function</b>. This density function is characterized by a <b>parameterized model</b> taken to be a mixture of component density functions; each component density describes one of the clusters. This model is then fit to the data by maximum likelihood or corresponding Bayesian approaches
    * Gausinan Mixtures: EM is a “soft” version of K-means clustering, making probabilistic (rather than deterministic) assignments of points to cluster centers. E-step of the EM algorithm assigns “responsibilities” for each data point based in its <b>relative density</b> under each mixture component; M-step recomputes the component density parameters based on the current responsibilities
    * Mode seeking - take a nonparametric perspective, attempt- ing to directly estimate distinct modes of the probability density function. PRIM algorithm is an example of mode seeking
  * k-means vs hierarchical clustering
    * K-means or K-medoids clustering algorithms de- pend on the choice for the number of clusters to be searched and a starting configuration assignment. In contrast, hierarchical clustering methods do not require such specifications. Instead, they require the user to specify a measure of dissimilarity between (disjoint) groups of observations, based on the pairwise dissimilarities among the observations in the two groups
  * Hierarchical Clustering
    * Agglomerative (bottom-up): the pair chosen for merging consist of the two groups with the smallest intergroup dissimilarity
    * Divisive (top-down): The split is chosen to produce two new groups with the largest between-group dissimilarity
    * Both paradigms there are N − 1 levels in the hierarchy
    * Possess a monotonicity property, the dissimilarity between merged clusters is monotone increasing with the level of the merger, so that the height of each node is proportional to the value of the intergroup dissimilarity between its children
    * dendrogram - The terminal nodes representing individual observations are all plotted at zero height
  * Agglomerative Hierarchical Clustering
    * <b>Single linkage (SL)</b> agglomerative clustering takes the intergroup dissimilarity to be that of the closest (least dissimilar) pair. 
    * <b>Complete linkage (CL)</b> agglomerative clustering (furthest-neighbor technique) takes the in- tergroup dissimilarity to be that of the furthest (most dissimilar) pair
    * <b>Group average (GA)</b> clustering uses the average dissimilarity between the groups
    * If the data dissimilarities {dii′ } exhibit a strong clustering tendency, with each of the clusters being compact and well separated from others, then all three methods produce similar results.
    * Compact - observations within them are relatively close together (small dissimilarities) as compared with observations in different clusters
    * SL can violate the “compactness” property that all observations within each cluster tend to be similar to one another. CL represents the opposite extreme, It will tend to produce compact clusters, but can violate the “closeness” property, that is, observations assigned to a cluster can be much closer to members of other clusters than they are to some members of their own cluster. GA represents a compromise between the two extremes of single and complete linkage, however its results depend on the numerical scale on which the observation dissimilarities dii′ are measured
  * Divisive Hierarchical Clustering
    * The recursive splitting continues until all clusters either become singletons or all members of each one have zero dissimilarity from one another.
  * Self-organizing Maps (SOM) can be considered as an online version of k-means, which means when you want to do clustering on streaming data, maybe SOM can be used
  
* Principle Components
  * Principal components are a useful tool for <b>dimension reduction</b> and <b>compression</b>
  * <b>Principal curves</b> generalize the principal component line, providing a smooth one-dimensional curved approximation to a set of data points. f(λ) is the average of all data points that project to it, that is, the points for which it is “responsible.” Each point on the curve is the average of all data points that project there.
  * <b>Principal surface</b> is more general, providing a curved manifold approximation of dimension 2 or more. 
  * <b>Principle points</b>: The set of k points that minimize the expected distance from X to its prototype are called the principal points of the distribution.
  * Principal surfaces have exactly the same form as principal curves, but are of higher dimension.

* Spectral Clustering
  * Traditional clustering methods like K-means use a spherical or elliptical metric to group data points, so will not work well when the clusters are non-convex. Spectral clustering is a generalization of standard clustering methods, and is designed for these situations. It has close connections with the local multidimensional-scaling techniques.
  * The idea in spectral clustering is to construct similarity graphs that represent the local neighborhood relationships between observations. Clustering is now rephrased as a graph-partition problem, where we identify connected components with clusters. We wish to partition the graph, such that edges between different groups have low weight, and within a group have high weight.
  * Choose params:
    * choose the type of similarity graph, such as fully connected or nearest neighbors
    * associated parameters, such as nearest of neighbors k or the scale parameter of the kernel c
    * choose the number of eigenvectors to extract from L
    * choose the number of clusters
  * Spectral clustering is related to <b>kernel principal components (kernel PCA)</b>, a non-linear version of linear principal components
    * An <b>eigenvector</b> or characteristic vector of a linear transformation is a non-zero vector whose direction does not change when that linear transformation is applied to it.
    * Standard linear principal components (PCA) are obtained from the eigenvectors of the covariance matrix, and give directions in which the data have maximal variance. Kernel PCA expand the scope of PCA, mimicking what we would obtain if we were to expand the features by non-linear transformations, and then apply PCA in this transformed feature space.
    * Kernel PCA is quite sensitive to the scale and nature of the kernel
    * Nearest-neighbor truncation of the kernel is important for the success of spectral clustering.
  * Sparse PCA
    * We often interpret principal components by examining the direction vectors vj, also known as <b>loadings</b>, to see which variables play a role.
    * Sparse loadings in this chapter, based on lasso (L1) penalties
    * PCA is applied to <b>shape data</b>, and is a popular tool in morphometrics. The features used for PCA are the sequence of coordinate pairs for each landmark, unpacked into a single vector.Sometimes, the sparse principal components procedure gives a more parsimonious, and potentially more informative picture of the important differences.
    
* Non-negative Matrix Factorization (NMF)
  * It is a recent alternative approach to PCA, data and components are assumed to be <b>non-negative</b>
  * The drawback of NMF is, the solution found depends on the starting values, and it would seem to hamper the interpretability of the factorization.
  * Factor analysis models are typically wed to Gaussian distributions
  * Factor analysis can be seen to be modeling the <b>correlation structure</b> of the Xj rather than the <b>covariance structure</b>. This can be easily seen by standardizing the covariance structure. This is an important distinction between factor analysis and PCA.

* Independent Component Analysis (ICA)
  * ICA has emerged as a strong competitor to factor analysis, it relies on the non-Gaussian nature of the underlying sources for its success.
  * ICA is able to perform blind source separation, by exploiting the independence and non-Gaussianity of the original sources.
  * ICA applied to multivariate data looks for a sequence of orthogonal projections such that the projected data look as far from Gaussian as possible. With pre-whitened data, this amounts to looking for components that are as independent as possible. ICA starts from essentially a factor analysis solution, and looks for rota- tions that lead to independent components.
  * Exploratory Projection Pursuit - A graphical exploration technique for visualizing high-dimensional data. Their view was that most low (one- or two-dimensional) projections of high- dimensional data look Gaussian
  * ICA and exploratory projection pursuit are quite similar, at least in the repre- sentation
  
* Nonlinear Dimension Reduction and Local Multidimensional Scaling
  * Nonlinear Dimension Reduction, can be thought of as “flattening” the manifold, and hence reducing the data to a set of low-dimensional coordinates that represent their relative positions in the manifold. They are useful for problems where signal-to-noise ratio is very high, not as useful for observational data with lower signal-to-noise ratios.
  * Classical multidimensional scaling may not preserve the ordering of the points along the curve, because it judges points on opposite ends of the curve to be close together. In contrast, local multidimensional scaling may do a good job of preserving the ordering of the points along the curve, it preserves the local affine structure of the high-dimensional data. A lower dimensional representation is constructed that best preserves these local approximations.
