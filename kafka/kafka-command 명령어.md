# kafka-command line 명령어

- 명령어
- 자주 사용하는 명령어

### 작동
- zookeeper -> kafka 순으로 작동
- `-d` 옵션은 daemon으로 생성 
```
bin/zookeeper-server-start.sh config/zookeeper.properties
bin/kafka-server-start.sh config/server.properties
```

### 종료 
- kafka -> zookeeper 순으로 종료
```
bin/kafka-server-stop.sh config/server.properties
bin/zookeeper-server-stop.sh config/zookeeper.properties
```

### 토픽 보기
```
bin/kafka-topics.sh --zookeeper localhost:2181 --list 
```

### 토픽생성
- `--bootstrap-server`로 지정할 수도 있고, `--zookeeper`로 지정할 수도 있음

```
bin/kafka-topics.sh --create \
  --bootstrap-server localhost:9092  \
  --replication-factor 1 \
  --partitions 1 \
  --topic test123
```

```
bin/kafka-topics.sh --create \
  --zookeeper localhost:2181 \
  --replication-factor 1 \
  --partitions 1 \
  --topic test123
```

### 토픽 생성
```
/usr/local/kafka/bin/kafka-topics.sh --create --bootstrap-server localhost:9092 --replication-factor 1 --partitions 1 --topic test
```

## show the topic

```
/usr/local/kafka/bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --from-beginning --topic numtest
```

## show the topic partiton 1
```
/usr/local/kafka/bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --from-beginning --partition 1 --topic numtest
```

## delete the topic
```
/usr/local/kafka/bin/kafka-topics.sh --zookeeper localhost:2181 --delete --topic my_topic
```

## consumer groups check!
```
/usr/local/kafka/bin/kafka-consumer-groups.sh  --bootstrap-server localhost:9092 --list
```

## consumer status and offset check!
```
/usr/local/kafka/bin/kafka-consumer-groups.sh  --bootstrap-server localhost:9092 --group sr --describe
```

## consumer group delete
```
/usr/local/kafka/bin/kafka-consumer-groups.sh --zookeeper localhost:2181 --delete --group <group_name>
```

## topic leader follower check 
```
/usr/local/kafka/bin/kafka-topics.sh --zookeeper localhost:2181 --topic my_topic --describe
```

## server log check
```
cat /usr/local/bin/kafka/logs/server.log 
```

### 토픽 리스트

```
bin/kafka-topics.sh --list --zookeeper server1:2181,server2:2181,server3:2181,server4:2181,server5:2181
```