CommonCrawl-Parent
=========

CommonCrawl Project has Big Data Programs which run on top of the Common Crawl Dataset (available on AWS S3) to extract certain analytics out of the 500TB Dataset. Apart from extracting the analytics (e.g Usage of Google Ads) from the Dataset, CommonCrawl Synerzip Project also plans to compare Big Data Technologies (e.g MapReduce vs Apache Spark) performances benchmark when extracting such analytics.

CommonCrawl Metrics
-----

### Google Ads Counter
Google Ads Counter is the Big Data Analytics program which counts how many html pages in the CommonCrawl dataset used google ads and which type of google ads (text, text_image, image etc)

**Analytics Report**

| Run | Dataset Files | Total Web Pages | Google Ads Used | Google Text Ads | Google Text/Image Ads | Google Image Ads |
|-----|---------------|-----------------|-----------------|-----------------|---------------------------|------------------|
| 1 | TBD | TBD | TBD | TBD | TBD | TBD |
| 2 | TBD | TBD | TBD | TBD | TBD | TBD | 

**Technology Bench Mark**
   
| Run | Technology | Dataset Size | Cluster Descr | Total Runtime |
|-----|------------|--------------|---------------|---------------|
| 1 | Map Reduce | 800MB | 3x AWS Cluster Description | 23 min |
| 1 | Apache Spark | 800MB | 3x AWS Cluster Description | 28 min |
   


CommonCrawl-Projects
-----
Following are the Common Crawl Projects which are used for extracting analytics and benchmarking Big Data Technologies
* [CommonCrawl-MapReduce](http://github.com/synerzip/CommonCrawl-MapReduce) - Contains various Big Data Analytics for CommonCrawl Dataset based on Apache Hadoop's Map Reduce
* [CommonCrawl-Spark](http://github.com/synerzip/CommonCrawl-Spark) - Contains various Big Data Analytics for CommonCrawl Dataset based on Apache Spark, the newer Big Data Ecosystem
* [CommonCrawl-Common](http://github.com/synerzip/CommonCrawl-Common) - Contains the common code.

CommonCrawl Hadoop Cluster Setup
--------
This is the Big Data Experiment we are doing in Synerzip around Common Crawl Database

Setup :

6 xlarge ec2 nodes

Software:

Apache Spark v1.1.0
HDP 2.4 (Hortonworks Distribution)
Ambari 1.6


How to setup and execute CommonCrawl Project?
-----
TBD
Sumeet - Please convert all other md files to Markdown format (not html) and put links here

