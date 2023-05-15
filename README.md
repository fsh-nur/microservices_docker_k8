## What are microservices?

A microservice is a type of software architecture where a large application is broken down into smaller. independently deployable services. Each microservicers is responsible for a focused, specific business function. 

Microservices operate independently of each other, so teams are able to depoly and scale them respectively. They are resilient to failures, where if one microservice has an issue it will not impact the whole infrastructure or the overall reliability of the application.

## Difference between 2/N-tier and Microservices architecture?

N-tier architecture divides applications into layers on a single infrastructure, whereas microservices architecture splits up an application into multiple services that can communicate with each other using simple protocols such as HTTP. 2-tier architecture specifically is built on a client-server architecure and is deployed together, making scalability les flexible as both the app and database have to be scaled. However since microservice are more independent, they are more flexible, and easier to scale.

## What is Docker and conatinerisation?

Docker is an open-source platform which allows us to deploy and manage applications with isolated, lightweight containers. Containers are self-contained portable units which package an application including all of its dependencies and configurations. Dockers supports horixontal scaling by allowing multiple containers to run on a single, or distributed host. It also supports vertical scaling depending on demand. 

## Virtualisation VS Containerisation

In virtualization, multiple virtual machines are running, each with its own operating system, where as in containerisation, containers share the same operating host, howoever isolate the application and all its dependencies from the rest of the system.

Multiple containers can share the same host and resources,as well as being managed through platforms such as Docker and Kubernetes. In virtualization multiple instances of different operating systems are run on the same hardware with its own hardware resources, virtualised- each with it's own CPU, memory, storage etc.

Virtualisation incurs more costs since there are complete operating systems being run for each virtual machine, however with containerization, all containers can be run on the same operating system

## What is K8

