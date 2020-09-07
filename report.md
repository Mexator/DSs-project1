# Report for Distributed Systems Project 1.
Made by Anton Brisilin and Ruslan Israfilov

## Question 1. What is Docker-machine and what is it used for?

`Docker-machine` is a tool that allow you to manage your remote servers and
make them a Docker hosts. `Docker-machine` allows to install Docker 
Engine to almost any physical machine running any OS by wrapping it into a 
virtual machine.
This tool allows quickly create cluster of Docker hosts.

## Question 2. What is Docker Swarm, what is it used for and why is it important in Containers Orchestration? 
`Docker Swarm` is a container orchestration tool. It allows the user to 
manage multiple containers deployed across multiple host machines.
In a `Docker Swarm`, there are typically several worker nodes and at least 
one manager node that is responsible for handling the worker nodes' resources 
efficiently and ensuring that the cluster operates efficiently. `Docker 
Swarm` is important in Container Orchestration, because it can let us 
efficiently manage our resources in our Distributed Systems.

# Question 3. Install Docker-machine, create a machine, etc.
- **Docker Machine drivers**  
In our operating systems we have VirtualBox and VmWare Workstation installed.
However last one [is not supported](https://docs.docker.com/machine/drivers/) 
by Docker, at list officially, so we decided to use VirtualBox driver.
We installed a docker-machine (that was easy - it is in AUR repositories, 
so we just ran `yay -S docker-machine`)
- **Docker-machine provisioning**  
Actually, we don't really understood what to write there. We just ran 
`docker-machine create --driver virtualbox Master` and that created the 
docker machine. Afterwards we could connect to it with `docker-machine ssh 
Master`
- **Experiment with some docker-machine commands**  
Yes, we did it. 😄 We tried almost whole list of available commands. However,
we don't think that it is necessary to write what each one does.