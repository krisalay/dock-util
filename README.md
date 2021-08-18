![Krisalay|Dock Util](https://raw.githubusercontent.com/krisalay/dock-util/438e95352c7ec35c0f43243e5a95440c22d8900a/assets/banner.svg)

In some cases we want to have a levarage where we can install/unistall some services from our system. Additionally, we want to test some features with different versions of services like RabbitMQ, Redis, and many more.
Docker provides us this levarage, but again everytime we need some service to start we have to write all sort of commands, or we can use docker-compose to start our services.
This Dock Utility provides the functionality to fork up docker services upon need. With this utility, there is no need to get all the services installed in our system. Based upon our need, we can fork up the services.

## Services Included

- RabbitMQ
- Redis

## Prerequisites
- Docker installed in the system and accessible by non-root user

## Steps to use the utility
Run the following commands before using the utility
1. `make`

## Commands
**Start a RabbitMQ service**
```sh
./container rabbitmq start
```
Starts a RabbitMQ and its management plugin service on port 5672 and 15672 respectively.

**Stop a RabbitMQ service**
```sh
./container rabbitmq stop
```
Stops RabbitMQ and its management plugin service.

**Start a Redis service**
```sh
./container redis start
```
Starts a Redis service on port 6379.

**Stop a Redis service**
```sh
./container redis stop
```
Stops Redis service.

**Start a Redis CLI**
```sh
./container redis-cli start
```
Starts a Redis service on port 6379 and its CLI.

