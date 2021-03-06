# kafka-to-hdfs [![Build Status](https://travis-ci.org/jstanier/kafka-to-hdfs.svg?branch=master)](https://travis-ci.org/jstanier/kafka-to-hdfs)
Pipe the messages from a [Kafka](https://github.com/apache/kafka) topic into HDFS.

## Outline
This is much, much simpler than [LinkedIn](https://github.com/linkedin)'s [Camus](https://github.com/linkedin/camus), but it does the job for simple loads out of Kafka into HDFS. It's useful for taking a live sample of a Kafka topic for a period of time in order to run MapReduce on it later.

## Usage
Given a Kafka topic, the program will stream it into HDFS at the filename given. It will create new files every time the number of messages defined in `--messages.per.file` has been written.

## Required arguments
```sh
--zookeeper.host     e.g. zookeeper1
--output.path        e.g. hdfs://hdfs-cluster:9000/user/me/tweets.txt
--hdfs.site.xml      e.g. /Users/me/libraries/hadoop-2.6.0/etc/hadoop/hdfs-site.xml
--core.site.xml      e.g. /Users/me/libraries/hadoop-2.6.0/etc/hadoop/core-site.xml
--kafka.topic        e.g. query.mentions
--flush.size         e.g. 100
--messages.per.file  e.g. 10000
```


