# “Workshop: Big Data Warehouse Case Study with Amazon Redshift and S3”
* info@datakitchen.io
* Sybase

## Gil Benghiat,Chris Bergh & Eric Estabrooks, DataKitchen
* Saturday Workshop: The list of failed data warehouse projects is long. Operational projects often leave end-users, data analysts and data scientists frustrated with long lead times for changes and bug fixes. This case study will illustrate how to make changes to the data warehouse and dashboards quickly and with high quality. To start, we first look at a pharmaceutical launch, present the Seven Shocking Steps to Agile Analytics, explain Redshift and other Amazon Web Services (AWS) technologies, and show how to implement a Data Lake in AWS. The presenters then examine how to partition the work to teams and walk through examples on how to quickly implement features in the analytic system. Finally, we show how assets migrate between teams and review lessons learned. The speakers are the founders of DataKitchen and have decades of hands on and executive management experience in data, analytics, and software development and are current practitioners of Agile Analytics.

* Building a db for a pharmacutical company
* what is the business 
* What is the analytics process for?

* Fast vs. fragile

### Product launches in pharmaceuticals industry
* Analytics team is put toegether and data is coming from a variety of sources and 
* Terabites of data, not petabytes of data
* Mainly text data

* Less about reporting and more about delivering insight
  * Allow fast changes oto support investigative analytics and high quality production deliverables

1. Add tests througout your whole process
  * Are inputs free from issues
  * Are your business logic assumptions stil true
  * Are your outputs consistent
2. It's just Code: Branch & Merge
  * Access (python) transform (sql) model (R) visualize (Tableau) report (Excel)
  * Branch & Merging enables people to safely work on their own tasks (git source code control)
3. Use multiple environments
  * Your analytic works requires a coordinating tools and hardware (Stand one up in Amazon Redshift firing up a new cluster)
  * purpose of development, test, preview and production
  * Provide an analytic environment for each branch
    * add test to prove change works
    * EXCEPT (maybe ACCEPT) statement in redshift
    * Update production only after all tests are run
4. Modularize & Containerize
  * do not create on monolith of code
  * reuse the code and results
  * manage the environment for each
5. Give your analysts knobs
  * Some changes follow the 95-5 rule
6. Use Simple Storage
  * Data Lake (S3 Storage)
  * Data restore: be able to back up an restore your databases easily
  * Parameterize the process of lake to transformation to data warehouse
  * very often use secure FTP
  * The dta lake pattern
    * SFTP, S3, Relevant Separate Analtyic Enviro, Development for Busienss Analytst, Data Scientist, or Production
7. Support 3 workflows
  1. Small Team
  2. Feature Branch
  3. Data Governance (Comes after the fact for launch)

### Amazon Web Services 
* Why an Analytic Database?
  * optimized for read only queries
    * doesn't mean cant change tables, just improves speed of query
  * Poor transaction processing (aka OLTP
  * Rollback, multi-phase commits
* Under the hood
  * Compression
  * Store things in columns instead of row (just store columns themselves)
  * Parallel queries across clusters of machines
  * Support partitioning
* Column vs. Row Storage
* Parallel Queries
* Compression
  * most expensive is getting data to and from disks
* Amazon Redshift is an example of an analytic database 
  * Uses SQL
  * ODBC and JDBC drivers
  * INSERT/UPDATE/DELETE
    * Can COPY from S3 
  * Query was a lot faster for redshift vs. other 
  * Under 10 terabites use redshift instead of map reduce
  * For data lake EMR or S3--S3 less cheaper
*  Redshift optimization
  * Need to learn: DISTKEY, SORTKEY, COMPRESS (resorts), VACUUM (shrinks)
  * As of now, no great tool to optimize queries
    * Experiment
    * Build test timing harness and suite
    * Watch for long running queries from BI tool in AWS UI
* Redshift Mgmt
  * Clusters easy to clone (backup and restore from S3)
  * No stored procedures
  * Python Functions
  * Where to ETL?
    * On reshift
    * EMR
    * Scripts 
    * Hybrid
* Key based object store
  * s3://bucketname/path/to/object/sales.csv
  * can also turn on versioning for it
  * Or even use glacier to hold old data
  * could also you encription to lock down data so when not moving eveerything is safe
* Fire up EC2 Machines to fire up machines by the hour rest API has a ton of libraries python **boto**
  * Get data locally with sftp
    * Want to put in S3 at a certain time then use AWS Lambda doesn't need a server just starts python script based
    * Could also use Charan
    * Data pipelines Amazon's ETL tool 
    * AWS also has its own command line
* Data lake
  * Keep all your raw data
  * Used dates in the path to keep a full history
  * Standardized on dates or name
  * If costs get high, consider Glacier
  * Other than naming conventions are there other ways by tagging, keep the output of the transformations in the json, which serves as a coppy of the whole process
* Transform your data into target schemas
  * Redshift copy statement moves data from the s3 to a redshift table
  * Do your transforms in SQL
* Types of table sin Redshift
  * Raw, QA, Target Schema (eg: star)
  * Analytics hit Redshift with thier favority tools
* Could the rstudio be stood up in the EC2
  * Amazon has security groups with separate tcp

### Teams, Deliverables, Timing, Tools
* Data Supplier (Data Extracts Monthly)-RDBS, MDM, Salesforce, sFTP | Data Engineer (Organized, quality checked data set Weekly)- AWS,: S3, EC2, Redshift | Data Analyst (Insights via charts, graphs, dashboards, models daily) Tableau, Alteryx, Excel all use Jira
* Customers set priorities, requirements, and our focus
* Data analysts trying to empower business
* Data Supplier Team
  1. Monthly market surveys
  2. design the survey
  3. run the market survey
* Data Engineering Team
  1. Make a "scrappy star" in a data mart
  2. Send questions to supplier and keep analysts in the loop
  3. add data tests
  4. **Share star with data analyst team and get feedback**
  5. Iterate
  6. Release "solid star"
* Data Analytic Team
  1. Make scrappy dashboard
  2. Provide feedback to dat engineering team
  3. show early dashboards to users
  4. Have active build / design sessions
    * Make as many changes live as possible
  5. Publish production dashboards 70% there
    * Update changes

* Example: number of customers dropped, why?
  1. Investigate the root cause of the issue and why it was not dettected at data assebly time
  2. Root cause: Issue with production of supplier file
  3. Change test for % variation not absolut number




