# 1. Clone this repository
    cd docker-push-pull-project

# 2. Install express
    npm install express
    npm ci


# 3. test locally
    npm start
### then open http://localhost:8080
### you should see the test message
### or (if you are running EC2 machine), ec2-machine-ip:8080 in your browser and eadd inbount rule 8080 from security group

# 5. build Docker image (locally)
### tag name: bongodev/hello-docker:latest
    docker build -t YOUR_DOCKERHUB_ID/push-pull:latest .

# 6. Chec your image
    docker images

# 6. login to DockerHub to Push your image | provide your user name and PAT key
    docker login


# 7. push to Docker Hub
    docker push YOUR_DOCKERHUB_ID/push-pull:latest


# 8. run the pushed image locally (verify)
###  It tells Docker (and others) that the container is expected to listen on port 8080. It's more like a label that says “Hey, I'm using 8080 inside this container.
###  When you run the container: docker run -p 3000:8080 my-node-app, So the mapping means: "Hey Docker, if someone connects to my computer’s port 3000, please forward that traffic to port 8080 inside the container."
###  The host is your actual machine - your laptop, desktop, or cloud VM where Docker Engine is installed. A network port on your host OS - e.g., macOS, Windows, or Linux.

    docker run --rm -p 3000:8080 YOUR_DOCKERHUB_ID/push-pull:latest
### open http://localhost:8080 or <ec2-machine-ip>:8080

# Check your running containers:
    docker ps

# Check running and stopped 
    docker ps -a 

# stop container
    docker stop container_id

# Remove stopped containers
    docker container prune -a

# Remove images
    docker image prune -a
