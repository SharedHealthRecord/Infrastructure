# SHR Infrastructure
Deploy Share Health Record Infrastructure

## Prerequisite
* Docker

You can follow the following link to install Docker:
https://docs.docker.com/engine/install/ubuntu/

## How to use
As of now this repo creates a docker-cluster of HIE with following configuration
* 2 nodes of cassandra
* Mysql Container
* Identity server Container
* Terminology Server Container
* Health Id Server Container
* MCI Server Container

By default this brings up a fresh terminology server. If there is tr-dump available which we want to start with, we can put the dump file at `mysql/tr-dump.sql`. This will bring up a TR, initialized with the given dump file. We would need to change the openmrs global_property `webservices.rest.uriPrefix` to `http://localhost:9080/openmrs` after startup.


```
git clone git@github.com:SharedHealthRecord/Infrastructure.git
cd Infrastructure
./run-shr-cluster.sh
```
On some OS, it will require to use the following command `sudo ./run-shr-cluster.sh`. The above script has used `docker compose` command. Depending on Docker version someone will need to change the command to `docker-compose`.


We can find details setup guideline in the following link: https://sharedhealthrecord.github.io
