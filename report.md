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

# Question 4. Create two Workers as well
Screenshot of `docker-machine ls`:
![](q4.png)

# Question 5. Deploy a true container cluster farm across many Dockerized virtual machines.

To make this happen I did following:
1. Ssh to master. 
 - List IPs, choose one of them
 - Issue `docker swarm init --advertise-addr 192.168.99.100`. This created a 
 swarm with Mater node as a leader.
 - Also that gave me an instruction of how to join workers.
2. Ssh to worker 1.
```
docker swarm join --token [my-token] 192.168.99.100:2377
``` 
3. Ssh to worker 2.
```
docker swarm join --token [my-token] 192.168.99.100:2377
``` 
4. Ssh to master (again). 
- `docker node ls`  
 That showed that all nodes are connected and Master see workers.  

![](q5.png)