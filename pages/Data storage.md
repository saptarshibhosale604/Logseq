## Amazon Redshift #AWS
	- Data warehouse service
	- Collecting and storing data
	- Big data
	- datawarehouse cluster 01 => Leader node + compute node 01 + computer node 02 + ...
	- Client application => JDBC (Java DataBase Connector) / ODBC (Open DataBase Connector) =>
		- Leader node // manages interaction between client app and compute node, instructions to compute node =>
			- compute node 01 // execute the program, return result to leader node
			- compute node 02
			- ... // work in parallel
	- column storage // data storage in columnar format, structured
	- compression // column level compression
	- query editor // running redshift queries
	- dbt redshift logs => Datadog [[*]]
- ## AWS Lake Formation #AWS
	- building, securing, and managing data lakes
	- serverless
	- centralized repository
	- store all your structured and unstructured data
	- data at scale
	- central data catalog
	- Data Governance