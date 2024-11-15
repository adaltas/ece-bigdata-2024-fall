# Big Data project

## Subjects

The project has to focus on **Open Source distributed systems**. It can either be:

- A **technical project**, that can be installing a stack of technologies and/or writing code to process data on the stack. It has to include the **implementation**: code, configuration files. In this case:
  - The code has to be hosted on a **public Git repository**
  - The code has to be **documented** (READMEs, inline comments)
  - The **project report** has to include a clear description of the project, the steps to implement it and a list of problems encountered
- A **architecture/design project**, meaning that you will design a platform based on distributed systems for a particular use case. You will only write a project report that includes:
  - **Detailed description** of the use case
  - Presentation of all the technologies involved (at least 3)
  - Global architecture of the project (what technology for what part, interconnections between technologies)
  - The important thing here is to **explain why you picked a particular technology**, what other technologies were considered
  - Of course, you can implement pieces of the architecture, this will give you **bonus points**
  - Expected format for the report: PDF or Markdown

## Rating

## Due date

The project has to be finished for 26 Avril.

## Project examples

Technical:

- Implement a data pipeline that transports, stores and analyses machine logs (code includes: databases creation scripts, Java classes to write data to/from HBase, data analysis SQL scripts)
- Install Hadoop on a cluster of Raspberry Pi (code includes: Raspberry Pi configuration, READMEs detailing the installation steps)

Architecture/design:

- Uber wants to track all its drivers in real-time in order to predict the areas most likely to be in need for drivers (what technologies will be used to: transport data, store data, analyse data, present results, etc.)

## Adaltas Cloud links

- YARN: http://yarn-rm-2.au.adaltas.cloud:8088/ui2/index.html
- Zeppelin: http://zep-1.au.adaltas.cloud:9995/#/

## Distributed systems examples

- Platforms: Hadoop, Elasticsearch, Kubernetes
- Distributed storage systems: (HDFS), Rook, Ceph
- Blockchain
- Databases:
  - SQL: Hive, CockroachDB, Vitess
  - NoSQL: HBase, Cassandra/ScyllaDB, MongoDB, Neo4j
- Distributed processing frameworks: Hive, Trino
- Messaging systems: Kafka, RabbitMQ
- Stream processing engines: Flink, Kafka Streams
- Dataflow systems: NiFi
