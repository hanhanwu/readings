# readings


FREE DATA SCIENCE EBOOK/PUBLICATIONS

* Free O'Reilly Data ebooks: http://www.oreilly.com/data/free/
* Data Science in Fintech and Banking: https://github.com/hanhanwu/readings/blob/master/data-science-banking-and-fintech_comments.pdf
* Machine Learning Model Evaluation: https://github.com/hanhanwu/readings/blob/master/evaluating-machine-learning-models.pdf
* Reading Notes for ML Model Evaluation: https://github.com/hanhanwu/readings/blob/master/Evaluation_Metrics_Reading_Notes.pdf
* Big Data, Machine Learning with Transactional Data: https://github.com/hanhanwu/readings/blob/master/301_Kallerhoff_Machine_Learning.pdf
* Data Science publications to follow: https://www.analyticsvidhya.com/blog/2016/12/medium-com-top-14-handles-publications-to-follow-for-data-science/?utm_source=feedburner&utm_medium=email&utm_campaign=Feed%3A+AnalyticsVidhya+%28Analytics+Vidhya%29
* 27 Recommended Data Science Books: https://www.analyticsvidhya.com/blog/2019/01/27-amazing-data-science-books-every-data-scientist-should-read/?utm_source=feedburner&utm_medium=email&utm_campaign=Feed%3A+AnalyticsVidhya+%28Analytics+Vidhya%29
  * Some are really amazing, while the books are selling online, the authors also provided the .pdf free downloadable version, that's really kind!

***************************************************************

POTENTIAL BC ECONOMIC PERFORMANCE INDICATORS

* Key indicators (NLP needed for data parsing): http://www.bcstats.gov.bc.ca/StatisticsBySubject/KeyIndicators/KeyIndicatorsHighlights.aspx
* Economic and finance data from Statistic Canada (I could choose BC, CPI/GDP): http://www.statcan.gc.ca/tables-tableaux/sum-som/l01/cst01/dsbbcan-eng.htm
* Indicators of Capacity and Inflation Pressure, with historical data: http://www.bankofcanada.ca/rates/indicators/capacity-and-inflation-pressures/
* Building Permits by Community: https://github.com/hanhanwu/readings/blob/master/Building%20Permits%20by%20Community.pdf
* Building Permits by Regional District: https://github.com/hanhanwu/readings/blob/master/Building%20Permits%20by%20Regional%20District.pdf
* Labor Force Statistics: https://github.com/hanhanwu/readings/blob/master/Labour%20Force%20Statistics%2C%20September%202016%2C%20Highlights.pdf


***************************************************************

ABOUT CREDIT SCORING MODEL

* Detailed set of borrower's characteristics and many other issues to be noted: http://www.microfinancegateway.org/sites/default/files/mfg-en-paper-credit-scoring-in-microfinance-guidelines-based-on-experience-with-wwb-affiliates-in-colombia-and-the-dominican-republic-oct-2003.pdf
* MOGO digital finance: https://github.com/hanhanwu/readings/blob/master/MOGO_digital_finance.pdf


***************************************************************

DATA MINING/MACHINE LEARNING

* Free Machine Learning ebooks: https://github.com/rasbt/pattern_classification/blob/master/resources/machine_learning_ebooks.md
* Elements of Statistical Learning: http://statweb.stanford.edu/~tibs/ElemStatLearn/printings/ESLII_print10.pdf
  * Reading Notes: https://github.com/hanhanwu/readings/blob/master/ReadingaNotes_Elements_of_Statistical_Learning.md
* All of Statistics
  * Find the book here: https://www.amazon.com/All-Statistics-Statistical-Inference-Springer/dp/1441923225
  * Reading Notes: https://github.com/hanhanwu/readings/blob/master/ReadingNotes_AllOfStatistics.md
* Data Mining Bible: http://www.kvimis.co.in/sites/kvimis.co.in/files/ebook_attachments/Jiawei%20Han,%20Micheline%20Kamber,%20ian%20Pei%20Data%20Mining%203%20ed.pdf
  * Reading Notes for Data Mining bible: https://github.com/hanhanwu/readings/blob/master/ReadingNotes_DMBible.md
* Machine Learning Model Evaluation: https://github.com/hanhanwu/readings/blob/master/evaluating-machine-learning-models.pdf
  * Reading Notes for ML Model Evaluation: https://github.com/hanhanwu/readings/blob/master/Evaluation_Metrics_Reading_Notes.pdf
* Outliers Detection for Temporary Data
  * Book: https://www.amazon.com/Detection-Temporal-Synthesis-Knowledge-Discovery/dp/1627053751
  * Reading Notes: https://github.com/hanhanwu/readings/blob/master/ReadingNotes_Temporal_Outlier_Detection.md
  
  
-- PAPERS
* Fuzzy Histogram
  * Fuzzy Histogram vs Crisp Histogram: https://github.com/hanhanwu/readings/blob/master/fuzzy_histogram.pdf
    * According to this paper, fuzzy histogram can be both computational and statistically efficient, compared with crisp histogram.
  * Fuzzy Histogram and Density Estimation
    * Paper: https://www.lirmm.fr/~strauss/Publications/SMPS06.pdf
    * According to this paper, fuzzy histogram can deal with the discontinuous weakness of histogram density estimator, reducing the effect of arbitrariness of partitioning

* Tensorflow
  * 2015 paper: https://github.com/hanhanwu/readings/blob/master/whitepaper2015.pdf
    * No wonder this paper has so many authors
   
* Sequence to Sequence
  * LSTMs on sequence to sequence: https://github.com/hanhanwu/readings/blob/master/sequence-to-sequence-learning-with-neural-networks.pdf
    * They reversed the sequence, and therefore reduced the minimal time lag, frinally got surprused good results
    * The training data is huge and time couming (10 days training in their experiments)
    * language sequence here
    

-- Wiki
* Processing Mining: https://en.wikipedia.org/wiki/Process_mining
* The whole lecture about <b>Process Mining</b>: https://www.coursera.org/learn/process-mining/home/welcome
* The book, Process Mining: Data Science in Action: http://www.springer.com/gp/book/9783662498507
  * It seems that Process Mining is to use machine learning, data mining methods to manage process, you can think about it as ERP + Data Science.... (I'm trying to think whether this book will help my work than others)
* <b>Alpha Algorithm</b>: https://en.wikipedia.org/wiki/Alpha_algorithm
  * It does so by examining <b>causal relationships</b> observed between tasks. For example, one specific task might always precede another specific task in every execution trace, which would be useful information.
  * A lecture about alpha Algorithm: https://www.coursera.org/learn/process-mining/lecture/OlVtr/2-6-alpha-algorithm-a-process-discovery-algorithm
    * It only cares about <b>sequence of activities</b>
    * It discovers loops, concurrency and choices (key ingredients of process discovery)
    * Direct Succession: x>y iff for some case x directly followed by y
    * Casuality: x->y iff x>y and not y>x
    * Parallel: x||y iff x>y and y>x, means x sometimes followed by y, y sometimes follwoed by x
    * Choice: x#y iff not x>y and not y>x, means there is no case that one of them directly followed by the other
  * Patterns that Alpha Alg looks for:
    * Sequence Pattern: a->b
    * XOR-split pattern: a->b, a->c and b#c
    * XOR-join pattern: b->d, c->d and b#c
    * AND-split pattern: a->b, a->c, and b||c
    * AND-join pattern: b->d, c->d and b||c
  * Core Logic - By checking these patterns in a sequence, it generates footprint for each sequence, form a footprint matrix for events. Find such sets A, B, each element a in A should be followed by each element in B. This is what Alpha alg looks fofr based on the generated footprint. Meanwhile, (A,B) should be maximal to make the alg efficient, since the subsets of A, B should also satisfy.
  * Limitations
    * numbers beside () indicates the frequency, a () is called a trace
    * Loops of length 1: For example, these are the sequences [(a,c)2, (a,b,c)3, (a,b,b,c)2, (a,b,b,b,c)], and Alpha Algorithm will only see b||b, without getting how b is interacting with the rest
    * Loops of Length 2: For example, these are the sequences [(a,b,d)3, (a,b,c,b,d)2, (a,b,c,b,c,b,d)], and Alpha alg will only see b||c, without finding the connection between b,c and the rest
    * Non-local dependencies (challenging to many algorithms): For events that are not in direct following relationship, Alpha Alg won't find that relationship. So For example, there are 2 sequences A = [(a,c,d)45, (b,c,e)42], B = [(a,c,d)45, (b,c,d)42, (a,c,e)38, (b,c,e)22], they will from the same footprint, but is underfitting A
    * Mixed choices can also cause pfroblems, the result can be incorrect. For example, for a sequnence, [(a,c,d)45, (b,c,e)42, (a,c,e)20], the model generated by Alpha Alg will generate something does not exist in this sequence, such as (b,c,d). Alpha Alg can only find 1 to 1 transition, instead of finding multiple transitions have the same labels
  * Cannot deal with noise or incompleteness well, but many this type of algorithms cannot either. Frequency of traces in a sequence can influence the result
    * Noise: rare and infrequent behaviour that cannot represenr typical behaviour
    * Incompleteness: too few examples that can discover underlying structures
    * These 2 are fundational problems for all algorithms
  * Without negative examples, confusion matrix and F-score cannot be effective


***************************************************************

AI

* Bots
  * Recently I am seeing more and more about bots, need to know more about them :)
  * Conversational bots: https://github.com/hanhanwu/readings/blob/master/what-are-conversational-bots.pdf
    * While I can see opportunities about these bots, the way they train/build the conversational bots is scarying me. They use users' conversation data as sample data, even if they really won't discolse identity, I'm still worrying about my data privacy, because I always believe conversation style can disclose identity, and I dind't approve anyone to play with my private conversation data. Meanwhile, through this whole book, they dind't mention the data privacy issue. It makes me wonder whether these companies really respect conversation privacy.
    
* Practical Recommendations for Gradient-Based Training
  * https://github.com/hanhanwu/readings/blob/master/Practical%20Recommendations%20for%20Gradient-Based%20Training.pdf


***************************************************************

PSYCHOMETRICS

* Introduction of Psychometrics: http://www.alston.com/files/Publication/dec0a988-57ce-4ffe-ad7a-9c6a41a8422a/Presentation/PublicationAttachment/d5a1990d-a456-4d19-a4be-9f863dfce032/16-614%20FinTech%20Lending%20Update.pdf
* Examples of psychometrics: http://examples.yourdictionary.com/examples-of-psychometrics.html
* EFL- The Importance of Stakes for Psychometric Credit Scoring: https://www.eflglobal.com/the-importance-of-stakes-for-psychometric-credit-scoring/
* Psychometrics used in Peru Financial System: http://idbdocs.iadb.org/wsdocs/getdocument.aspx?docnum=38161685
* What to read: http://cogsci.stackexchange.com/questions/10721/how-can-psychometric-or-behavioural-tests-be-used-in-banking-to-evaluate-creditw
* CRAN Psychometric Models and Methods: https://cran.r-project.org/web/views/Psychometrics.html
* Small and Medium Enterprises (SMEs), the missing middle - https://www.hks.harvard.edu/centers/cid/programs/entrepreneurial-finance-lab-research-initiative/the-missing-middle
* EFL Modeling Methology (works well on small amount of data, even when the data is cross-country, avoid overfitting, using individual question instead of indexes of block of questions): https://www.eflglobal.com/wp-content/uploads/2014/09/EFL-Technical-Note-July-2012_s.pdf
* Enterprising Psychometrics and Poverty Reduction: https://www.hks.harvard.edu/fs/akhwaja/papers/EFLpaper2013.pdf
* A meta analysis on the relationship between business owners personality traits: https://github.com/hanhanwu/readings/blob/master/Let%20s%20put%20the%20person%20back%20into%20entrepreneurship%20research%20A%20meta%20analysis%20on%20the%20relationship%20between%20business%20owners%20personality%20traits%20business.pdf


***************************************************************

COMPUTER BASED PSYCHOLOGICAL ANALYSIS

* Computer based psychological analysis: https://github.com/hanhanwu/readings/blob/master/PNAS-2015-Youyou-1036-40.docx
* Psychological Questionare for academic use: http://discovermyprofile.com/
* MyPersonality Project: http://mypersonality.org/wiki/doku.php
* Personality and Business: https://github.com/hanhanwu/readings/blob/master/Let%20s%20put%20the%20person%20back%20into%20entrepreneurship%20research%20A%20meta%20analysis%20on%20the%20relationship%20between%20business%20owners%20personality%20traits%20business.pdf


***************************************************************

## BANKING KNOWLEDGE

* Credit Bureaus  — a company that collects information from various sources and provides consumer credit information on individual consumers for a variety of uses.
* BNI Score - Bankruptcy Navigator Index (BNI). a number that indicates the likelihood of an individual filing for bankruptcy. It is related to the better-known credit score, but unlike credit scores, bankruptcy risk scores are not sold to consumers by any of the credit bureaus.[1] Consequentially, individuals have little or no way of knowing what their bankruptcy risk scores are or how to improve upon them. Furthermore, since there is no standardized index of measurement, consumers often have trouble contextualizing their score on a standardized scale, instead only receiving general information from a single bureau http://www.creditcards.com/credit-card-news/bankruptcy-risk-score-1270.php
* Beacon score is a number generated by the Equifax Credit Bureau to rank an individual's credit-worthiness. Beacon scores are credit scores, which are determined through a complex algorithm. These numbers tell the lender how likely it is that the borrower will repay the loanBeacon score is a number generated by the Equifax Credit Bureau to rank an individual's credit-worthiness. Beacon scores are credit scores, which are determined through a complex algorithm. These numbers tell the lender how likely it is that the borrower will repay the loan. When NextGen FICO scores started being used, the Beacon score was replaced with the Pinnacle score.
* Credict Scores look similar: http://www.investopedia.com/terms/b/beacon-score.asp?layout=infini&v=5D&adtest=5D
* TDS - Total Debt Service Ratio,  http://www.investopedia.com/terms/t/totaldebtserviceratio.asp
* Social capital is a form of economic and cultural capital in which social networks are central, transactions are marked by reciprocity, trust, and cooperation, and market agents produce goods and services not mainly for themselves, but for a common good.
The term generally refers to (a) resources, and the value of these resources, both tangible (public spaces, private property) and intangible ("actors", "human capital", people), (b) the relationships among these resources, and (c) the impact that these relationships have on the resources involved in each relationship, and on larger groups. It is generally seen as a form of capital that produces public goods for a common good.
Social capital has been used to explain the improved performance of diverse groups, the growth of entrepreneurial firms, superior managerial performance, enhanced supply chain relations, the value derived from strategic alliances, and the evolution of communities.
* Tradeline: https://blog.smartcredit.com/2011/03/29/what-is-a-trade-line/
* Discretionary income: is the amount of an individual's income that is left for spending, investing or saving after taxes and personal necessities (such as food, shelter, and clothing) have been paid. Discretionary income includes money spent on luxury items, vacations and non-essential goods and services.
* Detached Housing: A single-family detached home, also called a single-detached dwelling, single-family residence (SFR) or separate house is a free-standing residential building. It is defined in opposition to a multi-family residential dwelling.
* Bank model and Fintech Focus: https://www.linkedin.com/pulse/fintech-ecosystems-banking-business-model-james-shanahan
* Transactional Analytics Customer Life Time: https://www.datasciencecentral.com/profiles/blogs/machine-learning-for-transactional-analytics-customer-life-time
  * The idea about defection rate for customers who are staying with the company in more years

### Digital Marketing
* Comprehensive Guide on Digital Marketing: https://www.analyticsvidhya.com/blog/2018/12/guide-digital-marketing-analytics/?utm_source=feedburner&utm_medium=email&utm_campaign=Feed%3A+AnalyticsVidhya+%28Analytics+Vidhya%29
  * It has a simple and straightforward way to describe how google ad biding system works
  * Cookies, Pixels and Tag Containers
    * All records a certain info about the website visitor
  * How cookies work when you go to another website but could still see relevant ads - data management platform

****************************************

Data Science in Leisure Time

* 10 must watch data science movies (to me, it means to watch the trailers, but it still looks exciting O(∩_∩)O~): https://www.analyticsvidhya.com/blog/2015/11/10-watch-movies-data-science-machine-learning/?utm_content=bufferb5186&utm_medium=social&utm_source=facebook.com&utm_campaign=buffer


****************************************

MYTHOLOGY

* Mythology of the Night Sky: https://github.com/hanhanwu/readings/blob/master/Mythology%20of%20Night%20Sky.pdf

****************************************

MARKETING & ECONOMY

* Research Checklist: https://github.com/hanhanwu/readings/blob/master/Ebook%20-%20The%20beginners%20guide%20to%20investing%20in%20ICOs.pdf
  * I think all types of marketing research should practice the checklists here
