# kafka-cli commands

========================= PRODUCER ========================

kafka-console-producer --broker-list localhost:9092 --topic topic-test

Example message: {"email":"test-kafka20@mail.com","password":"123456"}

————————————————————————————————————

========================= CONSUMER ========================

kafka-console-consumer --bootstrap-server 127.0.0.1:9092 --topic topic-test

kafka-console-consumer --bootstrap-server 127.0.0.1:9092 --topic topic-test --from-beginning

kafka-console-consumer --bootstrap-server 127.0.0.1:9092 --topic topic-test --group first-group
————————————————————————————————————

========================= TOPICS ========================

kafka-topics --zookeeper localhost:2181 --list

kafka-topics --zookeeper localhost:2181 --topic firstTopic --create --partitions 3 --replication-factor 1

kafka-topics --zookeeper localhost:2181 --topic topic-test --describe

kafka-topics --zookeeper localhost:2181 --topic firstTopic --delete

————————————————————————————————————

===================== CONSUMER GROUPS ====================

kafka-consumer-groups --bootstrap-server 127.0.0.1:9092 --list

kafka-consumer-groups --bootstrap-server 127.0.0.1:9092 --describe --group first-group

kafka-consumer-groups --bootstrap-server 127.0.0.1:9092 --group first-group --reset-offsets --to-earliest --execute --topic topic-test

kafka-consumer-groups --bootstrap-server 127.0.0.1:9092 --group first-group --reset-offsets --shift-by -2 --execute --topic topic-test
