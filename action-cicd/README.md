# How to create CI/CD with GitHub Action updated

## Create an EC2 machine with SSH_key (free tier sufficient)

### Install Docker in the EC2 Machine

    sudo apt update -y
    sudo apt install -y docker.io
    sudo usermod -aG docker $USER
    sudo reboot
    sudo systemctl status docker
    docker ps

### Add the following ports in security group:

    22, 80, 443, 5000

### From repository settings, add the folllowing Secrets

    AWS_HOST >> your EC2 machine_ip
    AWS_KEY >> key.pem text
    AWS_USER >> ubuntu, unless you created another user
    DOCKER_PASSWORD >> DockerHub PAT
    DOCKER_USERNAME >> DockerHub user_name

### Create a directory and copy the code from action.yaml to main.yaml filr

    .github/workflows/main.yaml

### Change some application file and push to gitHub, the gitHub action will trigger

This note was updated to trigger the GitHub Actions workflow from a small change in `action-cicd`.

### Hit <EC2_machine_ip>:5000 on the browser

    You will see your app on the browser
