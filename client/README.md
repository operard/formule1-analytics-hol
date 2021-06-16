# JHipster Installation



## Usage on Linux/Mac Windows (using Docker Toolbox)

Pull the image
Pull the latest JHipster Docker image:

docker image pull jhipster/jhipster


## Create a “jhipster” folder in your home directory:

mkdir ~/jhipster

## Run the Docker image, with the following options:

The Docker “/home/jhipster/app” folder is shared to the local “~/jhipster” folder

Forward all ports exposed by Docker (8080 for the Java application, 9000 for BrowserSync, 3001 for the BrowserSync UI)


docker container run --name jhipster -v ~/jhipster:/home/jhipster/app -v ~/.m2:/home/jhipster/.m2 -p 8080:8080 -p 9000:9000 -p 3001:3001 -d -t jhipster/jhipster


## Check if the container is running

To check that your container is running, use the command docker container ps:

CONTAINER ID    IMAGE               COMMAND                 CREATED         STATUS          PORTS                                                       NAMES
4ae16c0539a3    jhipster/jhipster   "tail -f /home/jhipst"  4 seconds ago   Up 3 seconds    0.0.0.0:9000-3001->9000-3001/tcp, 0.0.0.0:8080->8080/tcp    jhipster
Common operations


To stop the container run: 
docker container stop jhipster

And to start again, run: 
docker container start jhipster


# Accessing the container

The easiest way to log into the running container is by executing following command:

docker container exec -it <container_name> bash

If you copy-pasted the above command to run the container, notice that you have to specify jhipster as the container name:

docker container exec -it jhipster bash

You will log in as the “jhipster” user.

If you want to log in as “root”, as the sudo command isn’t available in Ubuntu Xenial, you need to run:

docker container exec -it --user root jhipster bash

