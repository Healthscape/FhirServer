# HAPI-FHIR HealthScape


## Introduction


This project provides a Docker Compose setup for running HAPI FHIR along with a PostgreSQL database, orchestrated by Docker Compose. HAPI FHIR is a powerful and flexible FHIR server that allows you to store and retrieve healthcare data using the FHIR standard.


A HAPI-FHIR HealthScape stack environment consists of the following:


- [HAPI FHIR JPA server](https://github.com/hapifhir/hapi-fhir-jpaserver-starter)
- [Postgres](https://github.com/postgres/postgres)
- [NGINX](https://github.com/nginx/nginx)


## Prerequisites


In order to use this project, you should have:


- [This project](https://github.com/Healthscape/FhirServer)
- [Docker](https://www.docker.com)


## Getting Started
1. Clone the repository:
```shell
    git clone https://github.com/Healthscape/FhirServer
    cd healthscape-fhir
```
2. Start the services:
```shell
    docker-compose up -d
```
This command will build the HAPI FHIR image and start the services defined in the docker-compose.yml file.
3. Access the HAPI FHIR server:
Now you can access the server using the https://localhost:443/fhir/ address as base URL.


## Configuration
The [docker-compose.yml](https://github.com/Healthscape/FhirServer/blob/main/docker-compose.yml) file contains configuration for the HAPI FHIR server, PostgreSQL database, and NGINX.


### HAPI FHIR JPA server


More about modifing the HAPI FHIR JPA server can be found on their official [github repository](https://github.com/hapifhir/hapi-fhir-jpaserver-starter).


### POSTGRES


The PostgreSQL configuration (database name, user, and password) can be customized in the docker-compose.yml file under the hapi-fhir-postgres service.


### NGINX
NGINX is used as a reverse proxy to route traffic to the HAPI FHIR server. All traffic is secured with self-signed certificates. The NGINX configuration can be found at [nginx/nginx.config](https://github.com/Healthscape/FhirServer/blob/main/nginx/nginx.conf)
