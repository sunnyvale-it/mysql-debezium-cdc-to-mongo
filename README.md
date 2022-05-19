
List DB test.tasks records

```console
$ docker exec -i mysql mysql -uroot -ppassword  <<< "select * from test.tasks;"
```

Insert a DB record in test.tasks table

```console
$ docker exec -i mysql mysql -uroot -ppassword  <<< "INSERT INTO test.tasks (\`title\`,\`status\`,\`priority\`,\`description\`,\`created_at\`)VALUES('test',1,1,'test',CURRENT_TIMESTAMP);"
```

List Kafka topics

```console
$ docker exec -i kafka /opt/kafka/bin/kafka-topics.sh --list --bootstrap-server=kafka:9092
```

Browse CDC Kafka topic

```console
$ docker exec -i kafka /opt/kafka/bin/kafka-console-consumer.sh \
  --topic mysql.test.tasks \
  --bootstrap-server kafka:9092 \
  --from-beginning \
  --property print.key=true \
  --property key.separator="-"
```


```console
$ docker exec -i mongodb mongo -u root -p password --quiet --eval  "db.getCollection('cdc').find().forEach(printjson)"
```


```console
$ docker exec -i mongodb mongoimport --authenticationDatabase admin -u root -p password --db test --collection cdc <<EOF
{
        "name": "denis"
}
EOF
```