# Kafka Python Project

This project uses Apache Kafka for communication between a producer and a consumer, both written in Python.

## Prerequisites

Make sure you have the following installed:
- [Docker](https://www.docker.com/get-started)
- [Docker Compose](https://docs.docker.com/compose/)
- [Poetry](https://python-poetry.org/docs/)

## Installation and Execution

### 1. Clone the repository
```sh
git clone https://github.com/dhiyego/kafka-py.git
cd kafka-py
```

### 2. Start the containers with Docker Compose
```sh
docker-compose up -d
```
This will start Apache Kafka, the Producer, and the Consumer.

### 3. Check logs
To check the producer logs:
```sh
docker logs -f producer_container
```
To check the consumer logs:
```sh
docker logs -f consumer_container
```

### 4. Stop the containers
```sh
docker-compose down
```

## Run Locally (Without Docker)
If you prefer to run without Docker:

### 1. Install dependencies
```sh
poetry install
```

### 2. Start Apache Kafka
If you do not have Kafka running, you can use a container:
```sh
docker-compose up -d kafka
```

### 3. Run Producer and Consumer
In separate terminals:
```sh
poetry run python producer.py
poetry run python consumer.py
```

## Project Structure
```
kafka-py/
│── docker-compose.yaml
│── producer.py
│── consumer.py
│── pyproject.toml
│── poetry.lock
│── Dockerfile.producer
│── Dockerfile.consumer
└── README.md
```

## Notes
- Ensure Kafka is running before executing the scripts.
- Adjust parameters in the code if necessary.
