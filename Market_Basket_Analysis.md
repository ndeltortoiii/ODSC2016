# “Business and Science Domain Applications of Big Data Analytics Using R”
## Prasad Saripalli / VP Engineering at Edifecs

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
