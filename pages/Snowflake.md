level:: 1
comment:: data warehouse, store, manage, and analyze large amounts of data
type:: software

- [[Intro]]
	- Cloud based data warehouse
	- Saas
	- Pay for use
	- Compute and storage separation for scaling
	- snowflake edition
		- standard, enterprise, business critical, virtual private sf
	- Support SQL
- Snowflake architecture
	- Multi-clustered shared data architecture
	- Centralized storage
	- Multiple compute clusters can access the same data simultaneously
	- node // virtual machine or server
		- Compute nodes // executing queries and performing computations on the data
		- Storage nodes // storing and managing the data in Snowflake
		- Leader nodes // managing the metadata and coordinating the activities
- Layers
	- Storage layer
	  collapsed:: true
		- Object storage => AWS, Azure, GCP
		- Immutable objects
		- micro partitioning
		  collapsed:: true
			- single file containing continuous segment of table data
			- smallest storage unit
			- 50 to 500 MB size
			- immutable
			- metadata
			- columnar format, compressed
			- auto partitioning
	- Compute layer
	  collapsed:: true
		- Compute engine // virtual warehouse
		- independent as storage
		- scalable, auto resumable
		- scale up // node ++
		- suspended // not in use, no credit use
	- Cloud service layer
	  collapsed:: true
		- Leader nodes
		- Security // Authentication and authorization // user management
		  collapsed:: true
			- User // entity, log in, perform action on snowflake db, assign one or multiple roles
			- Role // set of privileges, assign to user or other roles, child role, parent role
			  collapsed:: true
				- ACCOUNTADMIN
				- SYSADMIN
				- SECURITYADMIN
				- USERADMIN
			- Privilege // specific rights/ SQL queries, SELECT, UPDATE, INSERT, DELETE
			- Grant // assignment of a privilege to a role
			- Revoke // removal of a privilege from a role
		- requests load balancing
- Pricing
	- Storage, compute cost
	- Data X'fer out cost, data in free
	- cloud services // AWS Lambda, Azure Functions, to execute tasks and workflows
- Client tool
	- allows users to interact with the Snowflake database
	- web interface
		- worksheet
			- allows user to write and execute SQL queries
	- CLI // snow sql
	- Drivers and connectors // JDBC, ODBC, GO, Node JS, PHP, spark
	- session
		- temporary connection to the Snowflake database
		- to execute queries, load data, and perform other tasks
- Data loading
	- copy
		- stages => snowflake tables
		- snowpipe // for streaming data, serverless
			- event trigger when object placed in s3 bucket
			- s3 => snowpipe => snowflake
	- source => staging => warehouse
	- data format // csv, json, avro, parquet
- Data exporting
	- different formats
	- compressed, encrypted
	- export to
		- multiple files
		- database
		- s3
		- data warehouse
	- snowflake table => copy into => file
- Stage type
	- External Stage
		- storage location on cloud platform
		- s3 bucket, azure
	- Internal stage
		- temporary storage within snowflake
- Data X'mation while loading the data
	- copy
		- exclude one/ more columns
		- change order of cols
		- cast col into specific data types
		- truncate
- Table type
	- External tables
		- definition // snowflake metadata
		- data // external location
		- read only
		- no storage cost
	- Temporary table
		- temporary storage
		- Exist only for life time of a session
		- Not visible to other session
		- Time travel 1 day, failsafe 0 day
	- Transient table
		- temporary storage
		- persist between sessions
		- Time travel 1 day, failsafe 0 day
	- Permanent table
		- Default
		- store data indefinately
		- time travel 1 to 90 days, failsafe 7 days
- Continuous data protection
	- Time travel
	  collapsed:: true
		- Travel back to point in time
		- for db, schema, tables
		- time travel protection // retention period 1 to 90 days
		- if data get deleted by user => micro partitioned data do not get deleted, just metadata marked as 'deleted'
		- SELECT * FROM table01 AT( condition01 )
		- AT / BEFORE condition01
			- timestamp
			- offset // time difference
			- statement id
		- Undrop
	- Failsafe protection
	  collapsed:: true
		- Historic data recovery
		- after time travel period
		- access only by snowflake support
		- 7 days period // not changeable
- Zero copy cloning
	- Clone of the table, db, schema
	- no physical copying of source data
	- copying metadata, pointing to micro partition
	- time travel
	- fast operation
	- no extra storage cost
	- source and clone objects are independent of each other
- Secure data sharing
	- metadata operation
	- perform by cloud service layer
	- no physical data movement
	- fast operation
	- provider can stop sharing at anytime
	- no additional storage required
	- component
		- provider account // create share
		- share // data, table, db shared by provider
		- consumer account
	- Product offering
		- Direct sharing // one account to another account
		- Snowflake market place // 3rd party dataset, many to many
		- Data exchange // own private hub
		- Reader account // non snowflake customer
- Extending snowflake functionality
	- Snowpark: Snowpark API
		- Accessing and processing data from non sql programming languages
	- programming functions, stored procedure
	- Snowflake scripting
		- if else
		- loop
	- External functions
- Resource management
	- Resource monitor
		- track credit usage
		- defined quota
		- if usage > then suspend resource
		- not manage cloud services cost
	- System usage and billing
		- account admin => data => dbs => snowflake
		- Account usage schema
		- Information schema[]