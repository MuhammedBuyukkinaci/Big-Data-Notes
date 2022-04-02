# Big-Data-Notes
Listing my big data notes from [this Udemy Course](https://www.udemy.com/course/sifirdan-her-yonuyle-bigdata/)

## Section 1: Introduction to Big Data

1) If we want to label some data as big data, it has some properties as follows(known as 5V, sometimes 3 V or 11 V is used):

- Volume

- Velocity

- Variety

- Verification

- Value

2) A plane is generally having more than 5000 sensors. 10 GB data is created per second per engine in an airplane.

For a flight between Adana and Istanbul, the flight is taking 1 hour. The data created during this flight is

Data Generation Speed * Number of Engines * Total second of flight

10 GB * 2 engines * 3600 Seconds ~ 72 TB

3) An inforgraphics for social media is below

![Infographics](https://github.com/MuhammedBuyukkinaci/Big-Data-Notes/blob/master/images/001/000.png)

4) Variety means having different data sources like images, texts, audios, sensors, csvs, database tables etc.

5) Verification is that checking the data. For instance, speed value can't be negative or a probability can't exceed 1 etc.

6) Hadoop and spark are 2 most popular big data technologies. They are based on distributed computing.

7) Hadoop has 2 parts: HDFS and MapReduce. HDFS keeps data in a distributed way. MapReduce is processing data. Develop MapReduce in order to process data 

- Apache Pig
- Apache Hive

8) Spark has no storage part. It works on RAM, which leads to speed increase by 100 times compared to Hadoop.

9) If there are 5 machines in a cluster, 1 machine is master and remaining 4 machines are slaves. Data is replicated in hadoop by a replication factor.

![Cluster](https://github.com/MuhammedBuyukkinaci/Big-Data-Notes/blob/master/images/001/001.jpeg)

10) Data shouldn't be directly transferrred to Hadoop because it may lose. Kafka should receive data first and then data moves to hadoop secondly.

![Kafka](https://github.com/MuhammedBuyukkinaci/Big-Data-Notes/blob/master/images/001/002.jpeg)

11) NoSQL is essential in big data technologies because they are scalable. 4 types of NoSQL are as follows:

- Document: MongoDB and ElasticSearch. We can upload a json file to MongoDB.
- Wide Column: Hadoop, HBase, Cassandra
- Key Value: Redis, DynomoDB
- Graph DB: Neo4j, used in social media analysis.

![NoSQL](https://github.com/MuhammedBuyukkinaci/Big-Data-Notes/blob/master/images/001/003.jpeg)

## Hadoop

1) Hadoop is a java library which enables us to make parallel operations of big data(PB, EB) on multiple machines 

2) Hadoop composes of 4 components:

- Hadoop Common: Necessary for Apache Hive & Apache Pig It gives access them to access HDFS.

- HDFS: Hadoop distributed file system

- Hadoop YARN: It manages CPU, RAM and disk usage of MapReduce applications.

- Hadoop MapReduce: Tools to process data which is on HDFS.


3) HDFS can be examplified as follows:

![HDFS](https://github.com/MuhammedBuyukkinaci/Big-Data-Notes/blob/master/images/002/000.png)

4) MapReduce can be visualized as follows:

![HDFS](https://github.com/MuhammedBuyukkinaci/Big-Data-Notes/blob/master/images/002/001.png)

5) Hadoop has 3 modes in installation.

- Standalone mode: Used for debugging and testing

- Single Node Cluster: Replication factor = 1. Master and slave are the same.

- Multiple Node Cluster: Replication factor > 1, 1 master and others are slave. Hadoop should be installed in each machine and the network should be configured.

6) Cloudera is a platform in which hadoop, apache pig, apache hive, apache spark are installed. Install vmbox and install cloudera as an operating system.

7) Some hdfs commands on terminal of Hadoop is below:

```
# To create a directory on HDFS
hdfs dfs -mkdir /example

# To transfer a file to HDFS
hdfs dfs -copyFromLocal /path/of/file/in/local /target/directory/on/hdfs

# To see the number of files in a hdfs directory
hdfs dfs -count /example

# To see the content of a file in HDFS
hdfs dfs -cat /example/ratings.csv

# To copy a file in HDFS
hdfs dfs -copy /example/ratings.csv /var

# To delete a file
hdfs dfs -rm /example/ratings.csv

# To move a file to another directory
hdfs dfs -rm /example/ratings.csv /var

# To list files in usr folder
hdfs dfs -ls /us

# To change permissions of a file
hdfs dfs -chmod +x runall.sh

# To set replication factor of HDFS(should be used in a cluster where a master and slaves exist)
hdfs dfs -setrep 4 -R /example/ratings.csv

# Copy file to local
hdfs dfs - copyToLocal /path/in/hdfs /path/in/local

```

## Apache Pig

1) Apache is one of the ways to develop Map Reduce in Hadoop. It is processing data in HDFS.

2) We can develop Map Reduce via Java, Python, Scala, Apache Pig and Apache Hive. However, Apache Pig and Apache Hive are preferred.

3) Apache Pig is developed in Pig Latin language.

4) Pig file extension is `.pig`.

5) Some Apache Pig script is below:

```
# Loading data
First = LOAD '/data/*' USING PigStorage(',') AS
(
    userId: int,
    movieId: int,
    rating: double,
    duration: double,
    date: int,
    country: chararray
);

# To print data
DUMP First;

New_Data = FILTER First BY rating>3.0;

DUMP New_Data;

# Drop duplicate rows
New_Data2 = DISTINCT New_Data;

DUMP New_Data2;

New_Data3 = GROUP First BY COUNTRY;

DUMP New_Data3;

AVG_DATA = FOREACH New_Data3 {
    Generate
    group,
    AVG(Data.duration) as ortalama;
}

DUMP AVG_DATA;

-- Inner join
JOINED_DATA = JOIN Personal BY DEPT_ID, DEPARTMENT BY DEPT_ID BY LEFT_TABLE;

DUMP JOINED_DATA;

--Left Join
JOINED_DATA = JOIN Personal BY DEPT_ID LEFT OUTER, DEPARTMENT BY DEPT_ID BY LEFT_TABLE;


-- Saving
STORE JOINED_DATA INTO /path/to/hdfs/directory USING PigStorage(',');

```

6) To run pig script,

```
pig path/to/directory/filename.pig
```

7) Bind condition(?:) is 'if else' of Apache Pig.

a==3?'dogru':'yanlis'

8) We can make regex operations in Apache Pig.

9) Standard Aggregation functions like max, min, avg is possible in Apache Pig.

## Apache Hive

1) Apache Hive is a tool to develop MapReduce on Hadoop environment.

2) We write SQL Queries for Apache Hive.










