# Report for Distributed Systems Project 1.
Made by Anton Brisilin and Ruslan Israfilov

## Question 1. What is Docker-machine and what is it used for?

`Docker-machine` is a tool that allow you to manage your remote servers and
make them a Docker hosts. `Docker-machine` allows to install Docker 
Engine to almost any physical machine running any OS by wrapping it into a 
virtual machine.

## Question 1. What is Docker Swarm, what is it used for and why is it important in Containers Orchestration? 
`Docker Swarm` is a container orchestration tool. It allows the user to manage multiple containers deployed across multiple host machines.
In a `Docker Swarm`, there are typically several worker nodes and at least one manager node that is responsible for handling the worker nodes' resources efficiently and ensuring that the cluster operates efficiently. `Docker Swarm` is important in Container Orchestration, because it can let us efficiently manage our resources in our Distributed Systems.
