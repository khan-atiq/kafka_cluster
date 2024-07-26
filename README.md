# kafka_cluster
kafka


Check Broker Status
kafka-broker-api-versions --bootstrap-server kafka1:29092


Describe Topics and Partitions
kafka-topics --bootstrap-server kafka1:29092 --describe

List all broker
kafka-configs --bootstrap-server kafka1:29092 --entity-type brokers --describe

List all topics
kafka-topics --bootstrap-server kafka1:29092 --list

kafka-topics --bootstrap-server kafka1:29092 --describe

Create topic
docker exec -it kafka1 /bin/bash
kafka-topics --create --bootstrap-server kafka1:29092 --replication-factor 3 --partitions 1 --topic my-replicated-topic

kafka-topics --describe --bootstrap-server kafka1:29092 --topic my-replicated-topic

kafka-console-producer --broker-list kafka1:29092 --topic my-replicated-topic

kafka-console-consumer --bootstrap-server kafka1:29092 --topic notification --from-beginning



----------------------------
from client binary location /usr/local/kafka/bin
./kafka-console-producer.sh --broker-list 192.168.0.224:9092,192.168.0.224:9093,192.168.0.224:9094 --topic notification

./kafka-console-consumer.sh --bootstrap-server 192.168.0.224:9092,192.168.0.224:9093,192.168.0.224:9094 --topic test-topic --from-beginning
