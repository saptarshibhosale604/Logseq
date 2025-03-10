level:: 1
comment:: infrastructure-as-a-code, define and manage cloud and on-premises infrastructure resources
type:: tool

- [[Intro]]
	- Infrastructure as a code
		- easily reproduce and manage complex infrastructure configurations
	- open server
	- infrastructure version control
		- Immutable infrastructure
		- new update => separate config snapshot
	- Automated Server Orchestration
		- server provisioning
		- deployment, configuration, and management of servers
		- and managing the underlying infrastructure
	- Declarative code style
		- HCL language
			- HashiCorp Configuration Language
			- human-readable configuration language
		- You describe what you want to create, rather than how to create it
	- Support multiple providers
		- AWS
		- Azure
		- GCP
		- Kubernetes
		- Oracle cloud
	- Client only architecture
		- uses cloud providers api for provisioning the infrastructure
- Terraform life cycle and cmds
	- terraform init
		- Initialize the working dir
		- containing config files
	- terraform plan
		- create an execution plan 
		  to reach desire state of an infrastructure
		- => check current state and config file =>
		- list out steps to make current state == config file =>
	- terraform apply
		- make changes in the infra
		- follow the steps from the plan
	- terraform destroy
		- delete all the infra resources created from file01.tf
- working
	- input source =>
		- terraform config file
			- what to create
			- file01.tf
				- provider "provider name" // e.g. for aws, access to provider resources
					- IAM user
						- programmatic access key
						- policies
					- region
					- access key
					- secret key
					- provider alias
				- resource "resource type" resource name
		- tf state
			- up to date state of infra