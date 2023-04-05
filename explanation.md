#	Choice of the base image on which to build each container.

//Backend Container

Used node:14-alpine as the base image, alpine is a variant of Node.js that is used in minimizing image size.

//Client Container

Used a multi-stage build to separate the build environment from the production environment, allowed me to avoid including unnecessary build tools and files in the final image hence reducing the size of the image.

Used node:14-alpine at the build stage ,as the base image, alpine is a variant of Node.js that is used in minimizing image size.

Used node:14-alpine3.14 at the production stage ,as the base image, alpine is a variant of Node.js that is used in minimizing image size.

#	Dockerfile directives used in the creation and running of each container.

FROM: Specifies the base image 

WORKDIR: Sets the working directory for any RUN, CMD, ENTRYPOINT, COPY, and ADD instructions that follow it.

COPY: Copies files and directories from the host to the container.

RUN: Runs a command inside the container.

EXPOSE: Exposes a port from the container to the host machine.

CMD: Specifies the command to run when the container starts.

## In the docker-compose.yml file used to run the containers, the following directives are used

version: Specifies the version of the Docker Compose file format to use.

services: Specifies the different services (containers) to run.

build: Specifies the build context and Dockerfile for building the container image.

ports: Specifies the port mapping between the container and host machine.

volumes: Specifies the volumes to mount between the container and host machine.

depends_on: Specifies the order in which the services should be started.

# Docker-compose Networking (Application port allocation and a bridge network implementation) where necessary.

networks:
  my-network:
    driver: bridge

In Docker Compose, the networks directive is used to define networks for containers to connect to each other

    my-network is the name of the custom network being created

    driver: bridge specifies that the network driver to be used is the default bridge driver. 

#	Docker-compose volume definition and usage (where necessary).
  
   ## client
./client:/app - This is a bind mount volume that maps the local ./client directory to the /app directory inside the client container.It allows changes made to files in the ./client directory on the host system to be reflected inside the container.

/app/node_modules - This is a named volume that is created by Docker when the container is created. It is used to store the node_modules directory of the application, which contains all of the dependencies needed to run the application. Using a named volume ensures that the dependencies persist between container restarts.

./backend:/app - This is a bind mount volume that maps the local ./backend directory to the /app directory inside the backend container. This allows changes made to files in the ./backend directory on the host system to be reflected inside the container.

./backend/.env:/app/.env - This is another bind mount volume that maps the local ./backend/.env file to the /app/.env file inside the backend container. The .env file typically contains environment variables used by the application, and using a bind mount volume allows you to easily update these variables without rebuilding the container.


#	Git workflow used to achieve the task.

- Git Status: to check on available changes

- Git add .: to add the changes made

- Git commit -m :to explain the changes made before pushing

- Git push :to push the changes made into the respective directory

#	Successful running of the applications and if not, debugging measures applied.

The application runs successfully,yolo-backend-1,server listens on port 5000 and Database connected successfully

yolo-client-1.compiled succesfully and app can be viewed on the local host http://localhost:3000

#	Good practices such as Docker image tag naming standards for ease of identification of images and containers. 

Both images have been tagged as

- ddf6d9125f8c75c5e9a8ba80cedf9368f5f9aa8c87586a366d82ac8f5d498e4e :my-backend-image

- d491538a085f33b6b54e06d8a5bc6c335ba49f4bf0acb666c4b044509319a513 :my-client-image