# Docker cAdvisor Monitoring

This project sets up cAdvisor for monitoring Docker containers in real-time
## Features

- **Real-time container monitoring**: Track resource usage like CPU, memory, network, and disk.
- **Web-based dashboard**: View the metrics in a simple and interactive web UI.
- **Lightweight and simple setup**: Easy to get started with Docker and Docker Compose.
  
## Prerequisites

- Docker
- Docker Compose
- Basic knowledge of Docker containers

## Project Structure

The project consists of the following structure:
docker-project/ ├── docker-compose.monitor.yml # Docker Compose file for running cAdvisor ├── .gitignore # Git ignore file ├── README.md # This file


- **docker-compose.monitor.yml**: The Docker Compose configuration to set up cAdvisor.
- **.gitignore**: A file to exclude unnecessary files from version control.

## Setup

1. Clone the repository:
   ```bash
https://github.com/saiusha30/docker-cadvisor-monitoring.git

2. cd docker-project

## preinstalled

docker,
docker compose
## Set Up cAdvisor Using Docker Compose
The Docker Compose file provided in the project will set up cAdvisor in a container that will monitor other running Docker containers.

Run the following command to start cAdvisor:

docker-compose -f docker-compose.monitor.yml up -d

This command will pull the gcr.io/cadvisor/cadvisor:latest Docker image and run it.

cAdvisor will expose a web UI on port 8080 by default.

## Access the cAdvisor Dashboard

ip address:8080


## Running Your Own Containers
Once cAdvisor is running, it will automatically detect and show stats for any Docker containers running on the same machine.

For example, to run an Nginx container for testing:

docker run -d --name nginx-test -p 8081:80 nginx

You should now see the nginx-test container in the cAdvisor dashboard.

##Troubleshooting
If cAdvisor does not show containers, make sure that you have the necessary Docker volumes mounted correctly. In the docker-compose.monitor.yml file, ensure the following volumes are mounted:

/:/rootfs:ro

/var/run:/var/run:ro

/sys:/sys:ro

/var/lib/docker/:/var/lib/docker:ro

Ensure Docker is running and that the containers are started before accessing the cAdvisor dashboard.


##Conclusion
This project provides a simple and effective way to monitor Docker containers using cAdvisor. It’s ideal for real-time container stats but is not designed for long-term monitoring. For long-term data storage and advanced features, consider integrating cAdvisor with tools like Prometheus and Grafana.

##Author
saiusha30
