# Hello World With PHP

Need an operating system with Php and Apache. Search Docker Hub for php image https://hub.docker.com/search?q=php&type=image

Select official image https://hub.docker.com/_/php and look for apache on this page. **Apache with a Dockerfile** provides an instruction on how to use the image.

Source code of the docker file provides details about the image e.g. what operating system is used.

https://github.com/docker-library/php/blob/14a53e7cbf88bd59af72d086418844a3e0b4160a/7.4/buster/apache/Dockerfile

```
FROM php:7.2-apache            # Reuse base image from docker              
COPY src/ /var/www/html/       # Copy our file to the image
EXPOSE 80                      # Container will listen on port 80
```
## Build New Custom Image ~ my-php-app
Go to the project directory "php hello world" and run the 'docker build' command from the terminal

```
docker build -t my-php-image .
```

## Check the list of available Docker image on your system
```
docker image ls
```
>REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE <br />
>my-php-image        latest              488f5e62253f        4 minutes ago <br />


## Run New Container ~ my-php-container
Forward the port 80 on the host to port 80 on the container
```
docker run -p 80:80 --name my-php-container my-php-image
```

## Check the list of available Docker containers on your system
docker container ls 4fe7d2ad3da5

##Test the deployment
From the browser, enter
http://localhost:80
>Hello, World! — DaRealpunjabi

#Tidy things Up
Stop and remove the container and delete the image
```
docker container stop 4fe7
docker container rm 4fe7
docker image rm my-php-image
```
