level:: 1
comment:: automates the deployment, scaling, and management of containerized applications
type:: tool

- [[Intro]]
	- dockerized micro services
		- single server, multiple independent environments
	- container orchestration tool
		- automated arrangement, coordination, and management
		- monitor, scale, restart containers
	- Features
		- Managing multiple containers as one entity
		- Resource usage monitoring
		- Networking // containers communication with each other
		- Rolling update
		- Load balancing
		- Health checks, restart containers
- [[Architecture]]
	- Monolithic application (not using) vs micro service based application (using)
	- User => Ingress => Service => Deployment => Pods => Container
	- Pod // is a container, can contains multiple containers
	- Deployment // consist of pods
		- input = images of container
	- Service // internal load balancing
	- Ingress // depend on user input redirecting to correct service
	- by user, application can be accessed by any node ip
- [[Working]]
	- cluster
		- K-master 
		  // Schedule containers on the nodes,
		  Monitor nodes and containers running inside nodes,
		  Track of logs of operation inside nodes
			- K-node01
			  // doing actual jobs,
			  processing, api calls
			- K-node02
	- cmds
		- kubectl get nodes // get list of loads
		- kubectl get pods // list of pods
			- kubectl get po
		- kubectl create deployment deployment01 image01
		- kubectl create -f deploy.yml
		- kubectl delete deployment deployment01
		- kubectl create service service01 deployment01
		- kubectl delete service service01
	- deploy.yml
		- specification of deployment
		- replicas
		- image
		- port
		- app