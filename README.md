![Krisalay|Dock Util](https://raw.githubusercontent.com/krisalay/dock-util/438e95352c7ec35c0f43243e5a95440c22d8900a/assets/banner.svg)
![](https://img.shields.io/github/languages/count/krisalay/dock-util?style=for-the-badge) ![](https://img.shields.io/tokei/lines/github/krisalay/dock-util?style=for-the-badge) ![](https://img.shields.io/github/issues-raw/krisalay/dock-util?style=for-the-badge) ![](https://img.shields.io/github/v/release/krisalay/dock-util?style=for-the-badge) ![](https://img.shields.io/github/contributors/krisalay/dock-util?style=for-the-badge)

In some cases we want to have a levarage where we can install/unistall some services from our system. Additionally, we want to test some features with different versions of services like RabbitMQ, Redis, and many more.
Docker provides us this levarage, but again everytime we need some service to start we have to write all sort of commands, or we can use docker-compose to start our services.
This Dock Utility provides the functionality to fork up docker services upon need. With this utility, there is no need to get all the services installed in our system. Based upon our need, we can fork up the services.

## Services Included

- RabbitMQ
- Redis
- Elastic Search
- Kibana

## Prerequisites
- Docker installed in the system and accessible by non-root user

## Configurations
##### Redis
1. **Data Persistence**
If we want to persist the data in the host machine, then we can set the value of **REDIS_PERSIST_VOLUME=true** in *env* file. If its *false*, then the volume will be deleted once the container is stopped. 

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
Starts a Redis service on port 6379. It creates a docker volume with the name *redis_volume* at */var/lib/docker/volumes/redis_volume/_data*. By default it will create a temporary volume, which will be removed when the redis container stops. If you want to persist data and mount that data when the redis container starts, then you can set the value **REDIS_PERSIST_VOLUME=true** in *env* file. If its *false*, then the volume will be removed once the container is stopped. 

**Stop a Redis service**
```sh
./container redis stop
```
Stops Redis service. If the value of **REDIS_PERSIST_VOLUME** is set to *true* in *env* file then the data will be stored in the host machine and can be used by any new redis container or restarting the redis container. If its *false*, then the volume will be removed once the container is stopped. 

**Start a Redis CLI**
```sh
./container redis-cli start
```
Starts a Redis service on port 6379 and its CLI.

**Start an Elastic Search Container**
```sh
./container elastic-search start
```
Starts an Elastic Search service on port 9200.

**Stop an Elastic Search Container**
```sh
./container elastic-search stop
```
Stops Elastic Search service.

**Start Kibana Container**
```sh
./container kibana start
```
Starts Kibana service on port 5601.

**Stop Kibana Container**
```sh
./container kibana stop
```
Stops Kibana service.