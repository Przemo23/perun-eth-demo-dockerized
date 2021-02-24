# perun-eth-demo-dockerized
This repository contains a dockerized version of the original Perun demo (https://github.com/perun-network/perun-eth-demo)
It extracts the clients(Alice, Bob ad Carl) and the ganache service into separated containers and establishes
a connection between them in the default Docker subnet 172.17.0.0/16. As of now Carl is not able to either send or receive
any payments.

## Requirements
In order to run this version of you will be required to install the Docker Engine. A walkthrough of this process is described 
here: https://docs.docker.com/engine/install/.


## Running the demo
After cloning the repository enter the ganache directory and run following commands:
```sh
docker build -t ganache .
docker run -it -p 8081:8081 ganache

```
The next step is to activate the clients. Enter the corresponding directories and run in different consoles:
```sh
docker build -t alice .
docker run -it -p 8082:8081 alice

```
and
```sh
docker build -t bob .
docker run -it -p 8083:8081 bib

```
It is important to execute the commands in such order, otherwise the state channels won't be established.
The rest of the demo follows the rules of the original version. You are able to send payments, receive them
and benchmark the infrastructure.

The network is configured presuming that the user doesn't have any other running containers. If so you are required to
either modify the addressess in the network.yaml, alice.yaml and bob.yaml files or stop other containers.
