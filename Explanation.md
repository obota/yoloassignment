Explanation of Implementation Choices
Choice of the Base Image
In this project, we chose to use the official Node.js image from Docker Hub as the base image for both the client and backend containers. We chose this image because it provides a lightweight and secure environment for running Node.js applications, and it comes with Node.js and NPM pre-installed, which saves us the trouble of installing them manually.

Dockerfile Directives
In each Dockerfile, we used a few key directives to build the container image:

FROM: This directive specifies the base image to use for building the image. We used node:14-alpine as the base image for both containers.

WORKDIR: This directive sets the working directory for the container. We set the working directory to /app in the client container and /app/backend in the backend container.

COPY: This directive copies files from the host machine to the container. We used this directive to copy the application code and the package.json file to the container.

RUN: This directive allows us to run arbitrary commands in the container. We used it to install the application dependencies.

EXPOSE: This directive exposes a port to the outside world. We used it to expose port 3000 in the client container and port 5000 in the backend container.

CMD: This directive specifies the command to run when the container starts. We used it to start the application.

Docker-compose Networking
In the docker-compose.yml file, we used a bridge network to allow the client and backend containers to communicate with each other. We also specified the port mappings for the client and backend services, which allows them to be accessed from outside the Docker network.

Docker-compose Volume Definition and Usage
In this project, we did not use any Docker volumes as the application did not require persistent data storage. However, if we needed to persist data between container restarts, we could have used Docker volumes to achieve this.

Git Workflow
We used a simple Git workflow to achieve the task. We created a new branch for each feature and pushed the changes to the branch. Once the feature was complete, we created a pull request and merged it into the main branch.

Successful Running of the Applications
To run the applications, we built the client and backend Docker images using the docker build command and then used the docker-compose up command to start the containers. We were able to successfully run the applications by accessing the client at localhost:3000 in a web browser.

Docker Image Tag Naming Standards
To ensure ease of identification of images and containers, we followed the best practice of using descriptive and meaningful names for our Docker images and containers. For example, we used yolo-client:latest as the tag name for the client image and yolo-backend:latest as the tag name for the backend image.