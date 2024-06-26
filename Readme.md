# KafkaLab: Development Environment with Docker Compose

This Docker Compose setup provides a local development environment with Confluent Kafka, Schema Registry, Kafka Connect, Kcat, REST Proxy, Kafka UI, and Console. It's designed to be a scalable and easy-to-set-up tool for developers working with Kafka and related technologies.

## Prerequisites

- Docker and Docker Compose installed on your system.
- Basic understanding of Kafka and Docker.

## Services Included

- **Kafka**: A single-node Kafka broker with configuration supporting both broker and controller roles.
- **Schema Registry**: A service that provides a serving layer for your metadata. It is most commonly used for storing and retrieving Avro schemas.
- **Connect**: Kafka Connect with the Datagen Connector pre-loaded for easy data generation into Kafka topics.
- **Kcat**: A versatile Kafka CLI tool for producing and consuming data.
- **REST Proxy**: Provides a RESTful interface to a Kafka cluster.
- **Kafka UI**: A web UI for viewing Kafka cluster data and structures, hosted by [Provectus](https://github.com/provectus/kafka-ui).
- **Console**: A web application for Kafka cluster management and observation, hosted by [Redpanda](https://github.com/redpanda-data/console).

## Quick Start

1. Clone/download the necessary scripts and files from the provided source.
2. Navigate to the base directory of this project that contains the `docker-compose.yml` file.
3. Run `docker-compose up -d kafka` to start Kafka service.
4. Run `docker-compose up -d <<SERVICE>>` to start any of the below services:
   - Kafka: 9092 (external), 29092 (internal)
   - Schema Registry: 8081
   - Connect: 8083
   - REST Proxy: 8082
   - Kafka UI: 8080 (web interface)
   - Console: 8090 (web interface)

## Important Notes

- Ensure the `./update_run.sh` script is present as per the command setup for Kafka. This script is crucial for initializing or updating your Kafka setup.
- The `./data/1` directory is used for Kafka data persistence. You may need to create it if it doesn't exist.
- For the Console service, a configuration file `redpanda-console.yml` is expected in the `./` directory, make sure it exists and is properly configured.
