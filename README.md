# Docker Installation in Windows 

## 1. Install Ubuntu

Open Microsoft Store and install Ubuntu.

## 2. Set up Ubuntu

Run the Ubuntu application and finish the basic configuration.

## 3. Update and Upgrade packages

In the ubuntu console run the following commands:
~~~
sudo apt-get update -y
sudo apt-get upgrade -y
~~~

## 3. Add the stable channel repository

In the ubuntu console run the following commands:

~~~
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
~~~

## 4. add docker key to ubuntu

In the ubuntu console run the following commands:

~~~
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo apt-get update -y
~~~

## 5. Install the latest Docker CE

In the ubuntu console run the following commands:

~~~
sudo apt-get install -y docker-ce
~~~

## 6. Add user to docker group to run docker using non root user.

In the ubuntu console run the following commands:

~~~
sudo usermod -aG docker $USER && newgrp docker
~~~

## 7. Check version

In the ubuntu console run the following commands:

~~~
docker --version
~~~

If no error appears, docker must be turned on and configured in this step.

## 8. (optional) Run docker daemon:

In the ubuntu console run the following commands:

~~~
sudo dockerd
~~~

## 9. (optional) Configure Docker to start on boot

In the ubuntu console run the following commands:

~~~
sudo systemctl enable docker.service
~~~

## 10. (optional) TO disable this use below command:

In the ubuntu console run the following commands:

~~~
sudo systemctl disable docker.service
~~~

# Install containerd.io

## 1. Install containerd.io

In the ubuntu console run the following commands:

~~~
sudo apt-get install -y containerd.io
~~~

## 2.(optional) Configure containerd.io to start on boot

In the ubuntu console run the following commands:

~~~
sudo systemctl enable containerd.service
~~~

## 3.(optional)  To disable this use below command:

In the ubuntu console run the following commands:

~~~
sudo systemctl disable containerd.service
~~~

# Install Docker Compose

## 1. Install Docker Compose

In the Windows terminal run the following commands:
~~~
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
~~~

## 2. Create symbolic link for easy execution

In the Windows terminal run the following commands:
~~~
sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
~~~

## 3. Assign execute permissions

In the Windows terminal run the following commands:
~~~
sudo chmod +x /usr/local/bin/docker-compose
~~~

## 4. Check Docker Compose version

In the Windows terminal run the following commands:
~~~
docker-compose --version
~~~

# Basic Help Commands:

## 1. Check Ubuntu Status

In the Windows terminal run the following commands:
~~~
wsl -l -v
~~~

## 2. Run and connect Ubuntu

In the Windows terminal run the following commands:
~~~
wsl
~~~

## 3. Exit Ubuntu console

In the ubuntu console run the following commands:
~~~
exit
~~~

## 4. Run docker with WSL

In the Windows terminal run the following commands:

~~~
wsl sudo service docker start
~~~

## 5. Check docker version

In the Windows terminal run the following commands:

~~~
wsl docker version
~~~

## 6. List images docker

In the Windows terminal run the following commands:

~~~
wsl docker image ls
~~~

## 7. List containers run

In the Windows terminal run the following commands:

~~~
wsl docker ps
~~~

## 8. List all containers

In the Windows terminal run the following commands:

~~~
wsl docker ps -a
~~~

## 9. Shutdown Containers

In the Windows terminal run the following commands:

~~~
wsl docker stop ___ID CONTAINER or NAME___
~~~

## 10. Delete Container

In the Windows terminal run the following commands:
~~~
wsl docker rm ___ID CONTAINER or NAME___
~~~

## 11. Run docker compose File

To run a docker compose file, start windows terminal in the file's containing folder and then run the following command.
~~~
wsl docker-compose up -d
~~~

## 12. Connect to container

To run a docker compose file, start windows terminal in the file's containing folder and then run the following command.
~~~
wsl docker container attach my_docker_image
~~~
