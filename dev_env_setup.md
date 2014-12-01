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



<h3> How to run Map Reduce locally using Eclipse Luna</h3><br/>
<ol>
<li>Download the code <br/>
<code> cd $PROJECT_HOME </code><br/>
<code>git clone https://github.com/Synerzip/GoogleAdsExplorer-MapReduce.git</code>
</li>
<li>Import as maven project in Eclipse Luna</li>
<li>Create a launch profile for com.synerzip.warc.hadoop.CommonCrawlJob and add these parameters as<br/>
<code>-in  s3n://$access_key:$secret_key@aws-publicdatasets/common-crawl/crawl-data/CC-MAIN-2014-35/segments/1408500800767.23/warc/CC-MAIN-20140820021320-00000-ip-10-180-136-8.ec2.internal.warc.gz -out  /home/synerzip/aws/output -accesskey $access_key -secretkey  $secret_key -overwrite -maxfiles 1</code></li>
<li>Run CommonCrawlJob as java application</li>
</ol>
<i>hadoop used local job runner to run the map reduce on local machine, there is no explicit requirement of preconfigured hadoop </i>

<h3> How to run Spark job locally using Eclipse Luna</h3><br/>
<ol>
<li>Download the code <br/>
<code> cd $PROJECT_HOME </code><br/>
<code>git clone https://github.com/Synerzip/GoogleAdsExplorer-Spark.git</code>
</li>
<li>Import as maven project in Eclipse Luna</li>
<li>Create a launch profile for com.synerzip.warc.spark.GoogleAdsPageCount and add these parameters as<br/>
<code>-master local   -in s3n://$access_key:$secret_key@aws-publicdatasets/common-crawl/crawl-data/CC-MAIN-2014-35/segments/1408500800767.23/warc/CC-MAIN-20140820021320-00000-ip-10-180-136-8.ec2.internal.warc.gz -out $output_dir -overwrite -accesskey $access_key -secretkey  $secret_key</code></li>
<li>Run GoogleAdsPageCount as java application</li>
</ol>


