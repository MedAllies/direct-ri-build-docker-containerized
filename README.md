# direct-ri-build-microsrvcs

 Build pom for RI microservices only. 

This contains instructions for cloing the DirectProject Java RI projects and building all components for microservices.

## Tools

The following tools are needed to perform the full build

* Maven
* Git
* JDK 8
* Ant
* Unzip
* Tar
* JQ (optional: for automated clone of all repositories)


## Clone repositories
Each module of the Java RI is contained within its own repository.  You can either manually clone each repository, or you could create an automated script to clone all repositories.  

## Build Components
All project using maven pom.xml files for the build lifecyle.  After cloning all repositories, switch to the `direct-ri-build-microsrvcs` directory and run the following command to build all components.

`mvn clean install`

## Microservices containerization orchestration

Microservices images should be build prior and ready to be used by `docker-compose`

To run containerized microservices use command below:

`docker-compose up`

Current orchestration will deploy microservices and dependencies listed below:

- `config-service` with deployment specified environmental variables
- `config-ui` with deployment specified environmental variables
- `msg-monitor` with deployment specified environmental variables
- `smtp-mq-gateway` with deployment specified environmental variables
- `msg-monitor` with deployment specified environmental variables
- `smtp-mq-gateway` with deployment specified environmental variables
- `xd` with deployment specified environmental variables
- `sta` with deployment specified environmental variables
- `james-server` with deployment specified environmental variables
- `mysql` as a database dependency with deployment specified environmental variables
- `rabbitmq` as a message broker dependency with deployment specified environmental variables

For a microservice specific information please go to the related project.