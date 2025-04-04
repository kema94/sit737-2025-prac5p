# Calculator Microservice

This project is a simple Calculator Microservice packaged with Docker. It demonstrates how to build, run, and publish a microservice container using Docker and Docker Compose.

##  Build the Docker Image

To package the microservice into a Docker image, run the following command from the project root:

docker build -t calculator-microservice .

## Test the Image Locally

Before deploying, test the microservice locally to ensure it's working as expected:

docker run -d -p 3000:3000 -e PORT=3000 calculator-microservice


- `-d`: Runs the container in detached mode.
- `-p 3000:3000`: Maps port 3000 on your host to port 3000 in the container.
- `-e PORT=3000`: Sets the required environment variable for the application.

You can verify the service is running by visiting `http://localhost:3000` in your browser.

##  Run with Docker Compose

To simplify container orchestration, you can use Docker Compose. Ensure a valid `docker-compose.yml` file exists in the root directory, then start the container with:

docker-compose up -d

This command will:

- Read the `docker-compose.yml` file
- Pull any necessary images if they are not available locally
- Create and start the container(s) in the background

##  Push the Image to Docker Hub

To make your Docker image available for others (or for use in deployment pipelines), you can push it to Docker Hub.

1. **Log in to Docker Hub**  
   
   docker login
  

2. **Tag the Image**  
   Tag the local image with your Docker Hub username and repository:
   
   docker tag calculator-microservice kema94/calculator-microservice:latest
  
3. **Push the Image**  
   Upload the tagged image to your Docker Hub repository:
   
   docker push kema94/calculator-microservice:latest
  
   Once published, the image can be pulled from anywhere using:

   docker pull mirahazall64/calculator-microservice:latest



