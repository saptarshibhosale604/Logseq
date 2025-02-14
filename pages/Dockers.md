level:: 1
comment:: package, ship, and run applications in containers
type:: platform

- [[Intro]]
	- Platform for building, running and shipping apps, consistently
	- run and function same on any machine
	- containers // isolated environment, on same machine
	- | Container | VM |
	  | isolated environment | abstraction of machine, physical hardware separation |
	  | fast to start | slow to start |
	  | less memory / resources, use same os of the host | take more memory / resources, different os for each VM |
	- Docker hub // docker cloud registry
	- tag // for versioning
- [[Architecture]]
	- Client => Rest API => Server / Docker engine
	- Containers = processes
		- for Windows => Windows / Linux containers
		- for Linux => Linux containers
		- for mac => Linux VM => Linux containers
- Workflow / [[Working]]
	- application + dockerfile // contains instructions to convert app to image
	- image includes
		- cut down os
		- runtime environment
		- app files
		- 3rd party lib
		- env variables
	- image => container => runs application
- cmds
	- Docker version // docker server version
	- docker build // packaging, app + dockerFile => image
	- docker image ls // image list
	- docker run image01 // run image01
		- docker run -it ubuntu // interactive mode, can take input
	- docker pull image02 // pull image02 from docker hub (cloud)
	- docker ps // list of containers
- Docker file
	- Contains
		- Build in images as libraries
		- Copy files to image/dir01
		- execute cmd
- extra
	- shell // program, 
	  takes input cmd, pass to os / kernel for execution