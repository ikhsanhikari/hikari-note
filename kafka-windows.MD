# start zookeeper
- ubah zookeeper.properties , dataDir

` .\bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties `


# start kafka

`.\bin\windows\kafka-server-start.bat .\config\server.properties`

# create topic

`.\bin\windows\kafka-topics.bat --create --topic hikari-event --bootstrap-server localhost:9092`
