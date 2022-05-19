FROM ubuntu/kafka:latest

RUN apt-get update && apt-get install -y curl

RUN mkdir /opt/connectors

RUN curl -L https://repo1.maven.org/maven2/io/debezium/debezium-connector-mysql/1.9.2.Final/debezium-connector-mysql-1.9.2.Final-plugin.tar.gz -o /tmp/debezium-connector-mysql-1.9.2.Final-plugin.tar.gz && \
    tar -xzf /tmp/debezium-connector-mysql-1.9.2.Final-plugin.tar.gz -C /opt/connectors && \
    rm /tmp/debezium-connector-mysql-1.9.2.Final-plugin.tar.gz