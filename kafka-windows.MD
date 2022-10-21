# start zookeeper
- ubah zookeeper.properties , dataDir

` .\bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties `


# start kafka

`.\bin\windows\kafka-server-start.bat .\config\server.properties`

# create topic

`.\bin\windows\kafka-topics.bat --create --topic hikari-event --bootstrap-server localhost:9092`

# produce something

`.\bin\windows\kafka-console-producer.bat --topic hikari-event --bootstrap-server localhost:9092`

# consume something

`.\bin\windows\kafka-console-consumer.bat --topic hikari-event --from-beginning --bootstrap-server  localhost:9092`
