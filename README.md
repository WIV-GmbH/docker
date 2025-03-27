# Development Environment for WIV Kirby CMS

## Required
- Node > 22
- Ubuntu on WSL 2 with Docker and Docker-Compose because Mounting Files from Windows into Docker has ver poor Performance (see Setup Notes)
    - [See Setup Dev Environment Below](#setting-up-dev-environment)

## Setup

Create .env in root with

    APP_ENV=development

This way your local Setup will be run as Development

## Start Development Environment
To Start your Dev environment simply run the following. This will 

    docker-compose up -d

## Deployment
Before you commit your changes you need to run

    npm run build

This will create the dist folder needed in Production. This Folder is commited to git.

## Setting up Dev Environment
1. Open Windows Power Shell as Administrator.
2. Install WSL
`wsl --install`
3. Install Docker in Ubuntu<br><br>
    1. Update Packages<br> 
    `sudo apt update && sudo apt upgrade -y`<br>
    2. Install Required Dependencies<br>
    `sudo apt install -y ca-certificates curl gnupg`<br>
    3. Add Docker’s Official GPG Key<br>
    `sudo mkdir -p /etc/apt/keyrings`<br>
    `curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo tee /etc/apt/keyrings/docker.asc > /dev/null`<br>
    `sudo chmod a+r /etc/apt/keyrings/docker.asc`<br>
    4. Add the Docker Repository
    `echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null`<br>
    5. Install Docker<br>
    `sudo apt update`<br>
    `sudo apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin`<br>
    6. Verify Docker Installation
    `sudo docker --version`
4. Allow Docker to Run Without sudo (Optional)
By default, Docker requires sudo. To use it without sudo:<br>
    1.  Add your user to the docker group:<br>
    `sudo groupadd docker`<br>
    `sudo usermod -aG docker $USER`<br>
    `newgrp docker`<br>
    2.  Test without sudo:<br>
    `docker info`<br>
5.  Create Project Folder in your Home Folder<br>
    `mkdir -p ~/projects/`
6.  Clone Project into projects

<br><br><br>
___