# “The Big Data Security Challenge: Identifying and Protecting Sensitive Data on an Enterprise Scale”

## Anhad Preet Singh / Technical Expert at Dataguise
* Abstract: The expansion of Big Data technologies has seen enterprises collect more and more data without understanding the landscape of its quantity and quality. With massive data lakes ingesting huge amounts ofdata, the security and compliance liabilities can be extremely detrimental to the execution of businesses. Moreover, it is not just the mere value of data, the uncertainty in where the sensitive data resides is sometimes a far bigger problem. So Big Data tools are faced with a twofold problem – the scalability of search in big datastores and the precision in finding out exactly what data is sensitive.
* To solve the scalability problems, metadata can be very useful. More specifically, using structural information to infer the location of potentially sensitive data can tremendously help with reducing the amount of data that has to be read. If the structure of data is not known, then finding structure becomes the core problem. The precise classification of sensitive data, e.g. whether a 9-digit number is a Social Security Number or an ABA Routing Number, is a more complex problem, which may not even have a deterministic solution. This classification requires contextual information, machine learning and other techniques to make intelligently determine the right fit. The combination of scaling methodologies and intelligent disambiguation is what will help enterprises to secure their big data stores and drive maximum value out of their data assets.
* Bio: Anhad Singh, currently a Technical Lead at Dataguise, is leading the design and development of core Discovery at Dataguise. Prior to joining Dataguise, he got his PhD in Computer Science from the University of California, Davis. His research focused on the effectiveness of data anonymization and information privacy, for which he has worked on many projects with Lawrence Berkeley National Labs and UC Davis Medical Center. He also has a strong background in data analysis and security, which has helped him in creating data generation tools at Dataguise, to help test and break the product. He is also actively working with the product management and is an organizer for a monthly big data security and data governance meetup in the Silicon Valley.

* Why is a security company at an open data science conference

* Can we even anonymize data?
  * An Iterative Approach to Examining the Effectiveness of Data Sanitization
* aolstalker.com
* Latanya Sweeney if you have given DOB, Gender, Place (City/town/municipality), zip code can identify 87% of people just from teh census data

* Multiple source of data
* Multiple file types
* Multiple structures of data

### Data Centric Security

* Perimeter: Gaurding access to the cluster iteslf
  * Technical concepts: authentication, Network isolation
* Access: Defining what users and applications can do with data
  * Technical Concepts: permissions, authorization
* Data
* Visibility

* How do you identify what is sensitive data and then mask it
  * Get a copy that looks like real data, but with different results
* Should also mask cell level in structured data

* How do you do this masking with accuracy at scale
  * Accuracy
    * Expression Matching
    * Contextual information
    * Machine Learning
  * Scale
    * Sampling
    * Leverage Structures
    * Predictive Analysis

### Use Cases

* eBay data landscape - 132 TB of EDW data
  * Tell them which files are sensitive and which are not
  * **Need to make sure the repository is in PCI zone**
* American Express
  * First column very restrictive and then the new column is open access for data science

* How much data you have
* How much access do you have
* Where is it held

* **Focus on element level security and prove compliance, security, and breaches (Risks)
  * Allows value in business 
