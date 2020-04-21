<div align=center>
<img src="https://miro.medium.com/max/630/1*j_zP74-cpvXRcs8dM_pkMQ.jpeg" width="200" height="200"/>
</div>

# What is Docker?

- Docker is a system to create containers and run apps inside these containers
- It is used to solve compatibility issues and solve the matrix of hell issue
- It is an open source project which was developed in 2013
- Almost all the companies are slowly but surely switching to docker containers for their servers as they are more manageable than virtual machines
- Docker comes into play in the deployment stage of development.
- A container is just another process in one's computer
- A container can be built using something called docker images
- It was originally made only for Linux. Now it has also support for Windows. In a Mac, it runs on a virtual machine

# How to run a container in docker?

- We have to use the `docker container run` command.
- There are a lot of options with this command.
- The `--detach` or `-d` makes the container run in the background. The `--name` lets us name the docker container. The `-p` or `--publish` lets us specify the particular port on our system which routes to the port on the virtual network where the docker container is `port:docker` port.
- We can access the CLI inside a container by not using the `-d` tag and using a `-it` tag and making the container run with the command `bash` or `sh`.
- For example, `docker container run -it --name ubuntu ubuntu bash` can be a command to use the ubuntu image and access it using the CLI
- We can use `docker container ls -a` to list all the containers that have been created
- To delete we can do a `docker container rm` and add the name or id of the container after that. We can use the -f tag with it to delete a container thats already running
- To list all the images, we can do a `docker image ls -a` and to remove them `docker image rm` and then the image name.
- To run a bash in a container that has been stopped currently, we have to use the `docker start -ai name` . This is gonna work if the initial start command for that container was also a bash or sh.
- To get a CLI inside a running container, we can use `docker container exec -it name bash`

# Docker Networking

- To understand docker networks let us put it this way: My computer has an IP address at which all the traffic is coming. A NAT Firewall is blocking all that traffic from entering the virtual network of docker. And all outgoing traffic from the containers are NATed by the firewall.
- Now for the container to interact with the actual network, we have to use the -p tag while running a container and specify the port on our machine and a port on the dockers virtual network. Suppose we run `docker container run -d -p 8080:80 --name nginx nginx`, what we are actually doing is telling our network that all the incoming traffic on port 8080 on our system has to be forwarded to port 80 on the virtual network the container is connected to.
- Even without publishing a port on our IP Address, containers on a virtual network, which have a **different IP Address** can **interact with each other** because theyre **connected to the same network**
- We can also create multiple virtual networks and attach different containers to them. If two containers are on different virtual networks, the only way for them to interact is through the published ports for them on our machines
- For example **nginx** server is **8080:80** and **MySQL server** is on **3306:3306** on two different virtual networks with different IP Addresses, the only way they can interact is by sending data to port 8080 on the system from port 80 on one virtual network which forwards data to port 3306 on the system which then forwards data to port 3306 on the other virtual network where the MySQL container is running.
- `docker container port name` to show the port of a particular container
- `docker container inspect --format "{{.NetworkSettings.IPAddress}}" name` to show the IP Address of a particular container
- `docker network ls` shows all networks for docker
- `docker network inspect name` gives details about a particular network
- `docker network create name` to create a new network for docker(driver optional)
- `docker network connect [NETWORK] [CONTAINER]` to attach a network to a containere
- `docker network disconnect [NETWORK] [CONTAINER]` to detach a network from container
