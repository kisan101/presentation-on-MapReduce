## Presentation on MapReduce
- A programming model and an associated implementation for processing and generating large data
sets. Users specify a map function that processes a key/value pair to generate a set of intermediate
key/value pairs and a reduce function that merges all intermediate values associated with the
same intermediate key. Many real world tasks are expressible in this model.


# Hadoop Installation Process


Step 1: Click [here](https://drive.google.com/file/d/0BwIBPXSoIx_FTk1RN2IzMU9zMm8/view)here to download the Java 8 Package. Save this file in your home directory.

Step 2: Extract the Java Tar File.

Command: tar -xvf jdk-8u101-linux-i586.tar.gz

Step 3: Download the Hadoop 2.7.3 Package.

Command: wget https://archive.apache.org/dist/hadoop/core/hadoop-2.7.3/hadoop-2.7.3.tar.gz

Step 4: Extract the Hadoop tar File.
Command: tar -xvf hadoop-2.7.3.tar.gz

Step 5: Add the Hadoop and Java paths in the bash file (.bashrc).



## hadoop installation

### Haddop configuration files

Step 7: Open core-site.xml and edit the property mentioned below inside configuration tag:
core-site.xml informs Hadoop daemon where NameNode runs in the cluster. It contains configuration settings of Hadoop core such as I/O settings that are common to HDFS & MapReduce.

<?xml version="1.0" encoding="UTF-8"?>
<?xml-stylesheet type="text/xsl" href="configuration.xsl"?>
<configuration>
<property>
<name>fs.default.name</name>
<value>hdfs://localhost:9000</value>
</property>
</configuration>

Step 8: Edit hdfs-site.xml and edit the property mentioned below inside configuration tag:
hdfs-site.xml contains configuration settings of HDFS daemons (i.e. NameNode, DataNode, Secondary NameNode). It also includes the replication factor and block size of HDFS.

<?xml version="1.0" encoding="UTF-8"?>
<?xml-stylesheet type="text/xsl" href="configuration.xsl"?>
<configuration>
<property>
<name>dfs.replication</name>
<value>1</value>
</property>
<property>
<name>dfs.permission</name>
<value>false</value>
</property>
</configuration>

Step 9: Edit the mapred-site.xml file and edit the property mentioned below inside configuration tag:
mapred-site.xml contains configuration settings of MapReduce application like number of JVM that can run in parallel, the size of the mapper and the reducer process,  CPU cores available for a process, etc.

<?xml version="1.0" encoding="UTF-8"?>
<?xml-stylesheet type="text/xsl" href="configuration.xsl"?>
<configuration>
<property>
<name>mapreduce.framework.name</name>
<value>yarn</value>
</property>
</configuration>


Step 10: Edit yarn-site.xml and edit the property mentioned below inside configuration tag:
yarn-site.xml contains configuration settings of ResourceManager and NodeManager like application memory management size, the operation needed on program & algorithm, etc.


<?xml version="1.0">
<configuration>
<property>
<name>yarn.nodemanager.aux-services</name>
<value>mapreduce_shuffle</value>
</property>
<property>
<name>yarn.nodemanager.auxservices.mapreduce.shuffle.class</name>
<value>org.apache.hadoop.mapred.ShuffleHandler</value>
</property>
</configuration>



visit [here](https://www.edureka.co/blog/install-hadoop-single-node-hadoop-cluster)
