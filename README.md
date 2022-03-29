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





