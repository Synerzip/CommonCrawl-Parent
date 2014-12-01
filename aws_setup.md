==================To Do : Add screenshots


Suse linux server 11 SP3 for the experiment

1. Download scripts folder to \<PROJECT_HOME\>
2. <code>cd \<PROJECT_HOME\>/script</code>
3. Script will launch 3 on demand medium instances <br />
 <code> ./prepare-hdp.sh -v 1.1.0 -k \<name of key created on aws\> -i \<pem file path\> -a ami-88c841e0 -t m3.medium -u ec2-user --ebs-vol-size 8 launch bigdataexpt </code><br/>
4. Copy all the private ip's , these will be used at later stages<br />
5. Login to the ambari server <br />
	<code> ssh -i \<PEM file path\> ec2-user@\<public dns\> </code> <br/>
6. Switch to root account  <br/>
	<code> sudo -i </code> <br/>
7. Configure ambari  <br/>
	<code>ambari-server setup</code><br/>
	<i>Note: Keep all default settings i.e. just press enter for every option</i>
8. Start ambari server<br/>
	<code>ambari-server start</code> <br/>
9. On Chrome/Firefox Browse : http://\<public dns\>:8080 to get a login page <br/>
10. Use credentials admin/admin <br/>
11. Enter cluster name e.g bigdataexpt <br/>
12. Use hostnames copied in step 4 <br/>
13. Use all default settings, and use next button, select bare minimum services (hdfs, mapreduce,yarn, zookeeper & Tez)<br/>
14. Very likely you will get a warning of ntp service not started, to troubleshoot login to each machine <br/>
	<code>ssh -i \<PEM file path\> ec2-user@\<public dns\></code> <br/>
	<code>sudo -i</code><br/>
	<code>/etc/init.d/ntp start</code><br/>
15. Deploy cluster<br/>
16. ssh to ambari server machine <br/>
	<code>ssh -i \<PEM file path\> ec2-user@\<public dns\></code><br/>
	<code>sudo -i</code><br/>
	<code>su - hdfs</code><br/>
17. Download spark binary i.e. tar file [pre-compiled for hadoop 2.4] <br/>
    <code>wget http://d3kbcqa49mib13.cloudfront.net/spark-1.1.0-bin-hadoop2.4.tgz</code><br/>
    <code> tar -xf spark-1.1.0-bin-hadoop2.4.tgz</code><br/>
    <code>cd spark-1.1.0-bin-hadoop2.4</code><br/>
18. Configure environment variables
	<code>export JAVA_HOME=/usr/jdk64/jdk1.7.0_45</code><br/>
	<code>export YARN_CONF_DIR=/usr/lib/hadoop/etc/hadoop</code><br/>

19.  Test if spark is configured correctly <br/>
	<code>./bin/spark-submit --class org.apache.spark.examples.SparkPi    --master yarn-cluster  --num-executors 3 --driver-memory 512m  --executor-memory 512m   --executor-cores 1  lib/spark-examples*.jar </code> <br/>
20. Test if spark can read file on hdfs <br/>
         <code> top > wordcount </code><br/>
         <code> hadoop fs -put wordcount /tmp/wordcount</code><br/>
	 <code>./bin/spark-submit --class org.apache.spark.examples.JavaWordCount --master yarn-cluster  --num-executors 3 --driver-memory 512m  --executor-memory 512m   --executor-cores 1  lib/spark-examples*.jar /tmp/wordcount 10 </code> <br/>





