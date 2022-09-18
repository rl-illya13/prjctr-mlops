## Build the container
    docker build -t prjctr-mlops-hw2:latest .

### Build the container with different Python version
    docker build --build-arg PYTHON_VERSION=3.8 -t prjctr-mlops-hw2:latest .

## Run the container
    docker run -p 8080:8080 prjctr-mlops-hw2:latest

### Test the container
Navigate to http://localhost:8080/docs to test the API.

## Push the container image to Docker Hub
    docker tag prjctr-mlops-hw2:latest illya13/prjctr-mlops-hw2:latest
    docker push illya13/prjctr-mlops-hw2:latest

### First time it might require 
    docker login

## Docker Hub
[illya13/prjctr-mlops-hw2](https://hub.docker.com/repository/docker/illya13/prjctr-mlops-hw2)