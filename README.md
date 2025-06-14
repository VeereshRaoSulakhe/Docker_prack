# Docker_prack
This is the repo setup for the handy information on Docker images and setup instructions

sudo apt update && apt install -y unzip jq net -tools
apt install openjdk-17-jdk -y
apt install maven -y && curl https://get.docker.com |bash
useradd -G docker dockeruser
usermod -aG docker ubuntu
usermod -aG docker ec2-user
------------------------------------------------------
#aws cli installation
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
#azure cli installation
curl -sL https://aka.ms/InstallAzureCLIDeb | sudo bash
------------------------------------------------------
#terraform installation on Ubuntu
Step 1: Update System Packages
Ensure your system is up to date:
sudo apt update && sudo apt upgrade -y


Step 2: Install Required Dependencies
Terraform requires some dependencies for installation:
sudo apt install -y gnupg software-properties-common curl


Step 3: Add HashiCorp Repository
HashiCorp provides an official repository for Terraform:
curl -fsSL https://apt.releases.hashicorp.com/gpg | sudo gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/hashicorp.list


Step 4: Install Terraform
Now, install Terraform using apt:
sudo apt update
sudo apt install terraform -y


Step 5: Verify Installation
Check if Terraform is installed correctly:
terraform -version


This should display the installed Terraform version.
Step 6: Enable Auto-Completion (Optional)
To enable Terraform command auto-completion:
terraform -install-autocomplete


-----------------------------------------
docker create <image>:tag  ->For creating a image
docker pull ngnix <tag like latest or specific version>
docker ps to list the containers
docker ps -a to list all the containers with any status
docker rm <container_id> to remove a container
ocker rm -f <container_id> to forcefully remove a container
dDocker rmi docker images -a -q to delete all the docker images
docker rmi docker ps -a -q
docker run <image> to run a container using image
docker run -d <image> to run a container in detached mode.
-----------------------------------------
A server contains 65535 ports
-----------------------------------------
Accessing a container from internet:
For accessing a container from the internet we need to enable the ports for the server and the container.
docker run -d -p 8000:80 ngnix
#Here 8000 is the host port and the 80 port is the container port 
-----------------------------------------
Docker image == base OS + application runtime + system dependencies + application dependencies
FROM is used to give the reference of the O/S to be used while creating a docker image.
FROM image-name:tag
-----------------------------------------
Remove commands for the docker containers:
Docker rm -f `docker ps -a -q`  ->used to remove all the running containers in the current server.
Docker rmi `docker images -a -q`  --> used to remove all the images in the server.
-----------------------------------------
Pushing a docker image from a local instance to docker hub.
To push an image to a docker repository first we need to login to docker hub and then push the image as below.
Docker push <dockerusername>/<image_name>:tag
This will push the docker image to the docker repository.
-----------------------------------------
Pulling a docker image from a docker hub:
To pull an image from docker hub we need to use below format
Docker pull <dockerusername>/<image_name>:tag
-----------------------------------------
