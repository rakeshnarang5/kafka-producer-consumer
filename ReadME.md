How to start KAFKA server on Mac

Start zookeeper

bin/zookeeper-server-start.sh config/zookeeper.properties 

Start Kafka server

bin/kafka-server-start.sh config/server.properties 

Kafka unable to acquire lock

Rm -R /tmp/kafka-logs

Kill Kafka Server if already running

# lsof -n -i :9092 | grep LISTEN
The PID should be the second column entry eg 7812 below
java 7812 root 205u IPv6 60200 0t0 TCP *:webcache (LISTEN)
Now kill the process
# kill -9 7812

Create a topic on Kafka 

bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic Kafka_Example

Start listening on topic

bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic Kafka_Example --from-beginning
