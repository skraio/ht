---
tags: []
---

List topics
```bash
docker-compose exec kafka kafka-topics --list --bootstrap-server kafka:9092
```

Create topic
```bash
docker-compose exec kafka kafka-topics --create --topic incoming-transactions --partitions 3 --replication-factor 1 --bootstrap-server kafka:9092
docker-compose exec kafka kafka-topics --create --topic privileged-transactions --partitions 3 --replication-factor 1 --bootstrap-server kafka:9092
docker-compose exec kafka kafka-topics --create --topic standard-transactions --partitions 3 --replication-factor 1 --bootstrap-server kafka:9092
```

Send message to topic
```bash
docker-compose exec kafka kafka-console-producer --broker-list kafka:9092 --topic incoming-transactions
```

Read messages of topic
```bash
docker-compose exec kafka kafka-console-consumer --bootstrap-server kafka:9092 --topic privileged-transactions --from-beginning
docker-compose exec kafka kafka-console-consumer --bootstrap-server kafka:9092 --topic standard-transactions --from-beginning
```
