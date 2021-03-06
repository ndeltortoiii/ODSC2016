# “Business and Science Domain Applications of Big Data Analytics Using R”
## Prasad Saripalli / VP Engineering at Edifecs

### Rules building for market basket analysis
* http://software.ucv.ro/~cmihaescu/ro/teaching/AIR/docs/Lab8-Apriori.pdf
* classification (Decision trees in order) and association rules (Interesting patterns)
* Apriori algorithm
* Coorlation not causation
* pool together and make a superset to create a confidence and then build the rule engine 
  * what are the likely rules that will describe
* take a minimum support or else you will end up with too many rules
* create transaction sets for each purchaser
* then you go over 2 sets, 3 sets, etc. look at support
* Set a minimum confidence threshold

### Unstructured data and Big Data
* http://www.mattblackwell.org/files/papers/bigdata.pdf
* Too many attributes, the curse of dimensionality
  * PCA
  * Unstructured data
* Definition of Big Data: Operationally unable to handle 4gb / 6gb of data more RAM then considered ram
* The code is large even if the algorithm is simple
* data intensive probelsm
  1. Subset the data
    * could use DBR api
    * alternaitve is you may not need all the attributes **PC (Principle Component) Analysis**
      * http://www.r-bloggers.com/computing-and-visualizing-pca-in-r/
  2. A rommp through bigmemory
    * loads only part of it into ram
  3. When you bring in Map Reduce
    * Hadoop Map Reduce
      * TM package if you want to play with R if you have a table with email string text values and classify it
      * **Could be useful for looking at common issues from everyone's emails**
      * **Strength:** Map reduce will help you reduce them into individual nodes and do the computations into theose individual notdes into specific ways all indexes to the same node and then recombine to get the results back to you (Word count)  download cloudera application
      * **Drawback:** How many problems can you actually divide and recombine easily (ex: averages and means). distributed systems need to be supervised, but challengine when node fails.  Enterprise versions of hadoop (google and horton works) address the problem of node failure.  Hadoop loads the data then removes, loads data again and removes
    * Apache spark came to solve the map r problem of load and reload datasets of ram
      * Benifit: reusable data file maps, rapid calculation for things like the stock market (in memory databases like IBM, but expensive)
  3. 

### Anomaly Detection
* http://www.itl.nist.gov/div898/handbook/eda/section3/eda35h.htm
* how would you predict anomalies in time series
* Ex: privacy anomaly

* what attributes are we sorting
  * individual attribute anomaly or
  * multiple attribute anomaly

* Z-scores and modified Z-scores

* Grubbs' Test for Outliers (https://en.wikipedia.org/wiki/Grubbs%27_test_for_outliers)
  * need to do statistical sorting--frequency counting, 
  * could also group in r and replace with other sythetic values

* Question: if non numerical data and identifify unstructured data, how do you go about finding anomalys from that data
  * Suppose it is categorical data ex: temperature trends low, mild, high, very high, etc. 
    * Frequency analysis on how many times those are occuring on your dataset
    * Highest frequency and lowest are the ones that stand out as anomalies
  * Spam email protection example
    * thousands of emails and identify spam--ayers Bayes algorithm
    * TM Package (Text mining package)
    * Could turn it into indicies by building a directory
    * Build a lexicon of 10/15 words
    * Count the frequency the words are coming in and then use the Ayers Bayes algorithm

* KNN (K nearest neighbor) Algorithm
  * classifier algorithm (https://cran.r-project.org/web/packages/kknn/kknn.pdf)
  * build a classifier rule engine
  * first you log the data into attributes
  * use pythagorus 
  * then use cartesian distance formula--weight, color, type
  * then sort by distances using KNN, path of least resistance used as a decisioin map
  * Normalization

* Build a recommender system
  * http://www.inf.ed.ac.uk/teaching/courses/inf2b/learnnotes/inf2b-learn-note02-2up.pdf 
  * summary(knn(train, test, cl, k = 1)) 
  * map reduce uses recommender systems to divy it up to multiple machines
    * rows are individual critics and the columns are the individual movies and the numbers are the ratings
      * this is how they look for vectors and then calculate the distances from there
      * why 2 people, what about the other people?
        * come up with a similarities weighted from everybody's recommendations (formula 6 in pdf above) 

* ID3 Algorithm Decision Tree
 * http://www.cise.ufl.edu/~ddd/cap6635/Fall-97/Short-papers/2.htm
 * information gain entropy
 * certain requirements
   * atttribute-value description
   * predefined cloasses
   * sufficient examples
 * Need attribute selection 
  * **This is extermely useful for determining projects and creating a decision tree for the type of analytics by creating survey for customer satisfaction
    * The engine would then also give you the accuracy 
    * could then subset and then area boost the trees to help get a good representation of the market as a way to deal with large data sets
 
 
