# Fedex-Logistics-Stream-Data-Pipeline
This repository provides a framework for building a data streaming pipeline using Kafka and MongoDB, aimed at visualizing logistics data through a dashboard

### Table of Contents

1. [Introduction](#introduction)
2. [Prerequisites](#prerequisites)
3. [Setup and Installation](#setup-and-installation)
4. [Usage](#usage)
5. [Schema Registry](#schema-registry)
6. [Kafka Producer](#kafka-producer)
7. [Kafka Consumer](#kafka-consumer)
8. [Data Visualization](#data-Visualization)


### Introduction

This project demonstrates a robust data processing pipeline using Kafka and MongoDB, designed for handling logistics data. The pipeline includes a Kafka producer that generates and publishes Avro serialized data to a Kafka topic. A Kafka consumer subscribes to this topic, validates, deserializes the Avro data, and then ingests it into MongoDB. Additionally, visualizations are created directly within MongoDB Atlas to provide insightful analytics and reporting capabilities for the logistics data

---

### Prerequisites

Before starting, ensure you have the following installed:

- Python (3.6+)
- Apache Kafka
- Confluent Kafka Python library (`confluent-kafka`)
- MongoDB

---

### Setup and Installation


1. **Install dependencies:**

   ```bash
     pip install -r requirements.txt
   ```   
2. **Set up Kafka and MongoDB:**

- Install and configure Kafka according to the official documentation.
- Set up MongoDB and create a database and collection for storing data.

### Usage
1. **Start Kafka:**
- Start Zookeeper and Kafka server.

2**Run Kafka producer:**

```bash
    python kafka_producer.ipynb
```
- This script reads data from data/logistics.csv, serializes it into Avro format, and publishes it to the Kafka topic fedex_logistics.

3. **Run Kafka consumer:**
- In this project, the Kafka MongoDB Sink Connector is utilized to establish a connection between Kafka and MongoDB, facilitating data transfer into MongoDB. Within this setup, the Kafka MongoDB Sink Connector operates as the consumer.
- The consumer script subscribes to fedex_logistics topic , deserializes Avro data, validates it, and ingests it into MongoDB.
----------------------------------------

### **Schema Registry**
- Avro schemas for serialization/deserialization are managed by Schema Registry to maintain compatibility between producer and consumer.

### **Kafka Producer**
- The Kafka producer script (kafka_producer.ipynb) serializes data into Avro format using an Avro schema fetched from Schema Registry, and publishes messages to Kafka.

### **Kafka Consumer**
- The Kafka consumer(Mongodb Sink Connetor) subscribes to the Kafka topic, deserializes Avro data using the schema fetched from Schema Registry and inserts valid records into MongoDB.

### **Data Visualization**
- Visualizing FedEx logistics information involves transforming the data stored in MongoDB into meaningful charts or graphs that provide insights into various aspects of the shipment.
- ![alt text](datainfo1.png)
- ![alt text](datainfo2.png)
- ![alt text](datainfo3.png)
