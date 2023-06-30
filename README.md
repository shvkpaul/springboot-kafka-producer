# Technologies Used

1. Language : Java 17
2. Framework : Spring Boot 3
3. Kafka
4. Maven
5. Swagger for documentation

# Build/Execute

Import this maven project in your IDE (I am using IntelliJ IDEA).
Please run docker/local-dev.yml -> services to set up kafka

* Navigate to docker composer file location -> cd .\docker\ 
* Start the Docker containers -> docker-compose -f local-dev.yml up
* Connect to one of the Kafka broker containers -> docker exec -it kafka1 bash
* Create a new topic on each broker -> kafka-topics --create --topic mytopic --partitions 3 --replication-factor 3 --bootstrap-server kafka1:9092,kafka2:9093,kafka3:9094
* Verify that the topic has been created -> kafka-topics --describe --topic mytopic --bootstrap-server kafka1:9092,kafka2:9093,kafka3:9094

Produce message in the kafka
* Connect to one of the Kafka broker containers -> docker exec -it kafka1 bash
* To produce message -> kafka-console-producer --topic mytopic --bootstrap-server kafka1:9092
* Type message you want to produce -> Hello

Consume message in the kafka
* Connect to one of the Kafka broker containers -> docker exec -it kafka1 bash
* To consume message -> kafka-console-consumer --topic mytopic --bootstrap-server kafka1:9092 --from-beginning



## Swagger documentation

Swagger : http://localhost:8091/swagger-ui/index.html

springboot-kafka.postman_collection.json can be imported in postman for testing.

