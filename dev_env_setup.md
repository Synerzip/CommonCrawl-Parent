

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


