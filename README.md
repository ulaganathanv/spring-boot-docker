# Dockerized Spring Boot Application

### This project is an example for Spring Boot with Docker implementation. 

## Commmands to build and start the application.
* $ docker build -f Dockerfile -t spring-boot-docker .
* $ docker run -p 8085:8085 spring-boot-docker

## Commands to list and remove the containers.
* $ docker ps - This will list the active available containers.
* $ docker ps -a - This will list all the containers.
* $ docker stop &lt;container name/id&gt; - To stop the container.
* $ docker rm &lt;container id/container ids with space&gt; - This will remove the particular container. 

## Commands to list and remove the images.
* $ docker images - This will list the images.
* $ docker rmi &lt;image id&gt; - This will remove the particular image. The associated container should be removed before removing the image.
  
## Commands to tag and push the image to Docker Hub
* $ docker build -t &lt;hub-user&gt;/&lt;repo-name&gt;[:&lt;tag&gt;] - To name the local images when build it.  
* $ docker tag &lt;existing-image&gt; &lt;hub-user&gt;/&lt;repo-name&gt;[:&lt;tag&gt;] - To retag the existing local image.  
* $ docker push &lt;hub-user&gt;/&lt;repo-name&gt;[:&lt;tag&gt;] - To push the docker image. If the tag is not specified then the tag defaults to latest.  

## Commands for Kubernets Deployment
* $ kubectl create deployment spring-boot-docker --image ulaginda/spring-boot-docker - To deploy the application to kubernets.  
* $ kubectl expose deployment spring-boot-docker --type=LoadBalancer --port 80 --target-port 8085 - To expose the application to Internet.  
* $ kubectl scale deployment spring-boot-docker --replicas=3 - To add additional replicas.  

* $ kubectl run spring-boot-docker --image=ulaginda/spring-boot-docker --port=8085 - To open a port when we start the container.  

## Commands for reference - Docker
* $ docker pull &lt;image name&gt; - To pull the image from docker hub.  
* $ docker run -it ubuntu bash - This will start the container in interactive mode and it will allow to interact with bash of the container i.e the bash session inside the container.  
To check we can execute the below command to see the release version of Ubuntu.  
cat /etc/*release*  
* $ docker run -d centos sleep 20 - This will run in the background.  
* $ docker run ubuntu:17.04 - This will help to run the container of specific version. This concept is called ***tagging***. Otherwise docker will pull the latest version. 
* $ docker exec &lt;container name&gt; &lt;command&gt; - To execute a command within the running container.  
  e.g docker exec &lt;container name&gt; cat /etc/hosts  
* $ docker run -p 80:5000 spring-boot-docker - This will map the local port 80 to container port 5000. This concept is called ***port mapping***. 
* $ docker run -v /opt/datadir:/var/lib/mysql mysql - This will persist the data in docker host from the container. This concept is called ***volume mapping***.
* $ docker run -i spring-boot-docker - This will wait for an input from the docker host i.e Standard Input from docker host.

## Commands for reference - Kubernetes
* $ kubectl get nodes - To see the list of nodes.  
* $ kubectl get pods - To see the list of pods.  
* $ kubectl get services - To see the list of services.  
* $ kubectl describe pod spring-boot-docker - To see the pod details.  
* $ kubectl describe service spring-boot-docker - To see the service details.  
* $ kubectl delete service spring-boot-docker - To delete the service.  
* $ kubectl describe deployment spring-boot-docker - To see the deployment details.  
* $ kubectl delete deployment spring-boot-docker - To delete the application.  
* $ kubectl logs &lt;pod id&gt; - To see the logs of the specific pod.  

