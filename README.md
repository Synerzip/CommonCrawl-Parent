CommonCrawl-Parent
=========

CommonCrawl Project has Big Data Programs which run on top of the Common Crawl Dataset (available on AWS S3, in .gz compressed format) to extract certain analytics out of the 500TB Dataset. Apart from extracting the analytics (e.g Usage of Google Ads) from the Dataset, CommonCrawl Synerzip Project also plans to compare Big Data Technologies (e.g MapReduce vs Apache Spark) performances benchmark when extracting such analytics.

CommonCrawl Metrics
-----

### Google Ads Counter
Google Ads Counter is the Big Data Analytics program which counts how many html pages in the CommonCrawl dataset used google ads and which type of google ads (text, text_image, image etc)

**Analytics Report** (Placeholder Data)

| Run | Dataset Files | Total Web Pages | Google Ads Used | Google Text Ads | Google Text/Image Ads | Google Image Ads |
|-----|---------------|-----------------|-----------------|-----------------|---------------------------|------------------|
| 1 |20-Aug-2014 (4 files) 217096 pages 3.384 GB [details](file-list/expt1.md) | 217096 | 32351 | 17952 | 13848 | 551 |
| 2 | 20-Aug-2014 (50 files) 2170180 pages 33.23 GB [details](file-list/expt2.md)| 2170180 | 315382 | 172888 | 136378 | 6116 | 
| 3 | 20-Aug-2014 (100 files) 4342561 pages 66.52 GB [details](file-list/expt3.md)| 4342561 | 631546 | 345571 | 274010 | 11965 | 
| 4 | 20-Aug-2014 (474 files) 20592231 pages 314.95 GB [details](file-list/expt4.md)| 20592231 | 3006593 | 1628771 | 1320939 | 56883 |
| 5 | TBD | TBD | TBD | TBD | TBD | TBD | 

**Technology Bench Mark** (Placeholder Data)
   
| Run | Technology | Dataset Size | Cluster Descr | Total Runtime |
|-----|------------|--------------|---------------|---------------|
| 1 | Map Reduce | 3.3 GB | 6 xlarge ec2 nodes| 5.6 min |
| 1 | Apache Spark | 3.3 GB | 6 xlarge ec2 nodes | 2.3 min |
| 2 | Map Reduce | 33.23 GB | 6 xlarge ec2 nodes| 19.75 min |
| 2 | Apache Spark | 33.23 GB | 6 xlarge ec2 nodes| 18.29 min |
| 3 | Map Reduce | 66.56 GB | 6 xlarge ec2 nodes | 39.12 min |   
| 3 | Apache Spark | 66.56 GB | 6 xlarge ec2 nodes | 27.91 min |
| 4 | Map Reduce | 314.95 GB | 6 xlarge ec2 nodes | 172.44 min | 
| 4 | Apache Spark | 314.95 GB | 6 xlarge ec2 nodes | 122.49 min | 

CommonCrawl-Projects
-----
Following are the Common Crawl Projects which are used for extracting analytics and benchmarking Big Data Technologies
* [CommonCrawl-MapReduce](http://github.com/synerzip/CommonCrawl-MapReduce) - Contains various Big Data Analytics for CommonCrawl Dataset based on Apache Hadoop's Map Reduce
* [CommonCrawl-Spark](http://github.com/synerzip/CommonCrawl-Spark) - Contains various Big Data Analytics for CommonCrawl Dataset based on Apache Spark, the newer Big Data Ecosystem
* [CommonCrawl-Common](http://github.com/synerzip/CommonCrawl-Common) - Contains the common code.


How to setup and execute CommonCrawl Project?
-----
Follow the guides provided below to setup and execute CommonCrawl Big Data Analytics on AWS 

* [Development Environment Guide](http://github.com/synerzip/CommonCrawl-Parent/blob/master/dev_env_setup.md) - Provides information on how to setup the development environment for Common Crawl BigData Analytics
* [Setup Guide - Hadoop Cluster on AWS](http://github.com/synerzip/CommonCrawl-Parent/blob/master/aws_setup.md) - Provides information on how to setup the AWS Hadoop Cluster
* [Run Guide - Hadoop Cluster on AWS](http://github.com/synerzip/CommonCrawl-Parent/blob/master/execute_on_aws.md) - Provides information on how to run the MapReduce and Spark code on Hadoop Cluster
