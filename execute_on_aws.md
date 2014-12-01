<h3> How to run Map Reduce On AWS</h3><br/>

<ol>
<li>If not set, Setup the cluster using steps described <a href="https://github.com/Synerzip/CommonCrawl-BigData-Experiment/blob/master/aws_setup.md">here</a>  </li>
<li>Download the code <br/>
<code> cd $PROJECT_HOME </code><br/>
<code>mvn install</code><br/>
</li>
<li>
copy <code>$PROJECT_HOME/target/GoogleAdsExplorer-MapReduce-0.0.1-SNAPSHOT-jar-with-dependencies.jar</code> on any aws instance.
</li>

<li>ssh to aws instance <br/>
 <code>ssh -i $PATH_TO_PEM_FILE ec2-user@$Public_Dns </code><br/>
<code>hadoop jar CommonCrawl-MapReduce-0.0.1-SNAPSHOT-jar-with-dependencies.jar com.synerzip.analytics.commoncrawl.googleads.counter.GoogleAdsCounterJob  -in  s3n://\<aws access key\>:\<aws secret key\>@aws-publicdatasets/common-crawl/crawl-data/CC-MAIN-2014-35/segments/1408500800767.23/warc/CC-MAIN-20140820021320-0000[0-4]*.gz -out /user/hdfs/common-crawl/mapr/output -accesskey \<access key\> -secretkey  \<secret key\> -overwrite -maxfiles 5</code><br /></li>
</ol>


<h3> How to run Spark job on AWS</h3><br/>

<ol>
<li>If not set, Setup the cluster using steps described <a href="https://github.com/Synerzip/CommonCrawl-BigData-Experiment/blob/master/aws_setup.md">here</a>  </li>
<li>Download the code <br/>
<code> cd $PROJECT_HOME </code><br/>
<code>mvn install</code><br/>
</li>
<li>
copy <code>$PROJECT_HOME/target/GoogleAdsExplorer-Spark-0.0.1-SNAPSHOT-jar-with-dependencies.jar</code> on aws instance where spark binary is installed.
</li>
<li>ssh to aws instance <br/>
    <code>ssh -i  $PATH_TO_PEM_FILE ec2-user@$Public_Dns </code><br/>
    <code>cd $SPARK_HOME </code><br/>
    <code>./bin/spark-submit --class  com.synerzip.warc.spark.GoogleAdsPageCount --master yarn-cluster   --num-executors 3 --driver-memory 1G  --executor-memory 512m   --executor-cores 1 $Path_to_GoogleAdsExplorer-Spark-0.0.1-SNAPSHOT-jar-with-dependencies.jar  -in  s3n://$access_key:$secret_key@aws-publicdatasets/common-crawl/crawl-data/CC-MAIN-2014-35/segments/1408500800767.23/warc/CC-MAIN-20140820021320-00000-ip-10-180-136-8.ec2.internal.warc.gz -out /user/hdfs/google-ads-output -overwrite -accesskey $access_key -secretkey  $secret_key -master yarn-cluster</code></li>
</ol>
