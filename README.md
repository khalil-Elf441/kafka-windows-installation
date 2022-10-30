# kafka-windows-installation

[Apache Kafka](https://kafka.apache.org/)  is an open-source distributed event streaming platform used by thousands of companies for high-performance data pipelines, streaming analytics, data integration, and mission-critical applications.

### Download Kafka

Download the latest Kafka release and extract it:
https://kafka.apache.org/downloads <br/>
```console
cd kafka_*
```

### Start the kafka environment

Kafka with ZooKeeper : Start all services

```console
.\bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties
```

```console
.\bin\windows\kafka-server-start.bat .\config\server.properties
```

### Create a topic to store your events

```console
.\bin\windows\kafka-topics.bat --create --topic orders --bootstrap-server localhost:9092
```

### Write events into the topic

```console
.\bin\windows\kafka-console-producer.bat --topic orders --bootstrap-server localhost:9092
```
```console
This is my first order
```



### Read events into the topic

```console
.\bin\windows\kafka-console-consumer.bat --topic orders --bootstrap-server localhost:9092
```
```console
This is my first order
```

