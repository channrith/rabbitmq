# RabbitMQ Docker Compose Setup

This repository provides a simple `docker-compose.yml` configuration to run RabbitMQ with the management plugin. It uses the `rabbitmq:3-management-alpine` image and persists data on the host machine via bind mounts.

## Prerequisites

- Docker (version 19.03 or later)
- Docker Compose (version 1.25 or later)

## Setup

1. **Clone the repository (if applicable)**:
    ```
    git clone <repository-url>
    cd <repository-directory>
    ```

2. Optionally, create a `.env` file to configure RabbitMQ's default user, password, and virtual host:
    ```
    RABBITMQ_DEFAULT_USER=your_username
    RABBITMQ_DEFAULT_PASS=your_password
    RABBITMQ_DEFAULT_VHOST=your_vhost
    ```
    Alternatively, the defaults are:

    - RABBITMQ_DEFAULT_USER=guest
    - RABBITMQ_DEFAULT_PASS=guest
    - RABBITMQ_DEFAULT_VHOST=/

## Running RabbitMQ with Docker Compose
To start RabbitMQ, run:
```
docker-compose up
```
This will download the RabbitMQ image (if not already cached) and start the container. RabbitMQ will be accessible through:
- #### AMQP (RabbitMQ Protocol): `localhost:5672`
- #### Management Web UI: `http://localhost:15672`
  - Default credentials: `guest` / `guest` (unless overridden in the `.env` file)