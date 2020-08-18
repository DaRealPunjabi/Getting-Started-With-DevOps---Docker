# Hello World With NGINX

Need an operating system with nginx. Search Docker Hub for php image https://hub.docker.com/search?q=nginx&type=image

## Run New Container ~ my-nginx-container
Go to the project directory "nginx hello world" to deploy an nginx container and forward the port 8080 on the host to port 80 on the container.   <br />

Run the following command in the terminal:
```
docker run -p 8080:80 --name my-nginx-container nginx:latest
```

##Test the Deployment
From the browser, enter
http://localhost:8080
>Welcome to nginx!  <br />

## Stop the Container
Key in ```Ctrl-C``` in the terminal

## Get the Container ID
Docker ps stands for “Process Status”, Show all containers. Run the following command in the terminal:
```
docker ps -a
```
>CONTAINER ID        IMAGE   <br />
>f3d2987205ec        nginx:latest  <br />

## Update the Container Image
Run the following command in the terminal:
```
docker cp ./src/index.html f3d2987205ec:/usr/share/nginx/html/
```

## Create a new image from a container’s changes
Commit a container’s file changes and settings into a new image. Run the following command in the terminal:
<pre><code>
<b>docker container commit &ltcontainer id&gt &ltnew image name:tag&gt</b> <br />
docker container commit f3d2987205ec darealpunjabi:version1 <br />
</code></pre>


## List Docker Images
```
docker images
```

>REPOSITORY                           TAG <br />
>darealpunjabi                        version1  <br />

## Run the New Image
Run the following command in the terminal:
```
docker run -p 8080:80 darealpunjabi:version1
```

## Test the deployment
From the browser, enter
http://localhost:8080
>Hello, World! — DaRealpunjabi
