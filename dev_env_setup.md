# Development Environment Setup

## Project Overview
Following are the Common Crawl Projects which are used for extracting analytics and benchmarking Big Data Technologies
* [CommonCrawl-MapReduce](http://github.com/synerzip/CommonCrawl-MapReduce) - Contains various Big Data Analytics for CommonCrawl Dataset based on Apache Hadoop's Map Reduce
* [CommonCrawl-Spark](http://github.com/synerzip/CommonCrawl-Spark) - Contains various Big Data Analytics for CommonCrawl Dataset based on Apache Spark, the newer Big Data Ecosystem
* [CommonCrawl-Common](http://github.com/synerzip/CommonCrawl-Common) - Contains the common code.

## Project Setup
### Checkout Projects
Checkout all the required projects
* $>mkdir CommonCrawl
* $>cd CommonCrawl
* $>github clone http://github.com/synerzip/CommonCrawl-Parent
* $>github clone http://github.com/synerzip/CommonCrawl-Common
* $>github clone http://github.com/synerzip/CommonCrawl-MapReduce
* $>github clone http://github.com/synerzip/CommonCrawl-Spark

### Build Projects
Follow the instructions below to build all the projects using Maven

* $>cd CommonCrawl/CommonCrawl-Common
* $>mvn clean install
* $>cd ../CommonCrawl-MapReduce
* $>mvn clean package
* $>cd ../CommonCrawl-Spark
* $>mvn clean package

### Local Dataset
Follow the instructions below to download few files from CommonCrawl to run the MapReduce and Spark project locally

* $>mkdir CommonCrawl/input
* $>mkdir CommonCrawl/outout
* Download [CC-MAIN-20140820021320-00000-ip-10-180-136-8.ec2.internal.warc.gz](https://aws-publicdatasets.s3.amazonaws.com/aws-publicdatasets/common-crawl/crawl-data/CC-MAIN-2014-35/segments/1408500800767.23/warc/CC-MAIN-20140820021320-00000-ip-10-180-136-8.ec2.internal.warc.gz) to input directory

### Eclipse Project Setup
Follow the instructions below to setup these projects on Eclipse

* Download [Eclipse Luna](https://www.eclipse.org/downloads/)
* Import all the Projects from CommonCrawl Directory using Maven Import option in Eclipse

### Run MapReduce Program
* Right click on CommonCrawl-MapReduce and click on "Run as > Run Configuration"
* Create a Java Application Run Configuration
* Choose com.synerzip.analytics.commoncrawl.googleads.counter.GoogleAdsCounterJob as Main Class
* Provide the following parameters "-in <path to CommonCrawl/input folder> -out <path to CommonCrawl/output folder> -overwrite -maxfiles 1"
* e.g "-in /Users/rohitghatol/Synerzip/CommonCrawl/input/ -out /Users/rohitghatol/Synerzip/CommonCrawl/output/  -overwrite -maxfiles 1"

### Run Spark Program
* Right click on CommonCrawl-Spark and click on "Run as > Run Configuration"
* Create a Java Application Run Configuration
* Choose com.synerzip.analytics.commoncrawl.googleads.counter.GoogleAdsCounter as Main Class
* Provide the following parameters "-in <path to CommonCrawl/input folder> -out <path to CommonCrawl/output folder> -overwrite -maxfiles 1"
* e.g "-in /Users/rohitghatol/Synerzip/CommonCrawl/input/ -out /Users/rohitghatol/Synerzip/CommonCrawl/output/"

