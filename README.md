# Dockerized Spring Boot Application

### This project is an example for Spring Boot with Docker implementation. 

## Commmands to build and start the application.
* $ docker build -f Dockerfile -t spring-boot-docker .
* $ docker run -p 8085:8085 spring-boot-docker

## Commands to list and remove the containers.
* $ docker ps - This will list the active available containers.
* $ docker ps -a - This will list all the containers.
* $ docker rm <container id> - This will remove the particular container. 

## Commands to list and remove the images.
* $ docker images - This will list the images.
* $ docker rmi <image id> - This will remove the particular image. The associated container should be removed before removing the image.
  
## Commands for reference
* $ docker run -it ubuntu bash - This will start the container in interactive mode and it will allow to interact with bash of the container i.e the bash session inside the container. 
