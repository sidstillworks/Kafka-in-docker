# Kafka-in-docker

#Kafka Topics commands
docker exec kafka \
kafka-topics --bootstrap-server kafka:9092 --create --topic quickstart —partitions 3 —replication-factor 2
kafka-topics --bootstrap-server kafka:9092 --list
kafka-topics --bootstrap-server kafka:9092 --topic topic1 --describe
kafka-topics --bootstrap-server kafka:9092 --topic topic1 --delete
kafka-configs --bootstrap-server localhost:9092 --alter --entity-type topics --entity-name quickstart --add-config retention.ms=31556952000
kafka-topics --bootstrap-server kafka:9092 --create --topic quickstart2  --config retention.ms=31556952000
kafka-topics --bootstrap-server kafka:9092 --create --topic quickstart5  --config cleanup.policy=compact
kafka-configs --bootstrap-server localhost:9092 --alter --entity-type topics --entity-name quickstart4 --add-config cleanup.policy=compact

#Kafka Producers commands
kafka-console-producer --broker-list kafka:9092 --topic quickstart
kafka-console-producer --broker-list kafka:9092 --topic quickstart --producer-property acks=all

#Kafka Consumers commands
kafka-console-consumer --bootstrap-server kafka:9092 --topic quickstart
kafka-console-consumer --bootstrap-server kafka:9092 --topic quickstart --from-beginning
