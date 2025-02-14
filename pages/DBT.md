level:: 1
comment:: open source, data x'mation
type:: tool

- [[Intro]]
	- Data Build Tool
	- Analytics
	- Transformation
	- Data snapshot
- Supported database
	- [[Snowflake]]
		- Warehouse // for computing
		- Worksheet // for querying
		- Roles
	- Multiple availability
- profile.yml
	- Configuration, credentials
	- snowflake user, role, db, wh, shcema, account, threads
	- Connection detail, snowflake account
- dbt cmds
	- dbt init // Initializing dbt on local machine
	- dbt debug // check config, dependencies, db connection
	- dbt run // run models, sql queries
	  collapsed:: true
		- dbt run --models dir01 // run models from dir01
		- dbt run --models dir01.model01 // run model01 from dir01
		- source01 // run for models with specific source01
		- tag01 // run on models with tag: tag01
	- dbt test // run test on models based on dbt_project.yml
	- dbt snapshot // run dbt snapshot
	- dbt seed // reference tables to lookup
- dbt_project.yml file
	- paths for test, macro, data, source(models), snapshot
	- Testing
	  collapsed:: true
		- build in test for individual columns
			- unique
			- not null
			- accepted values
			- relationships // return values which are not from the models specified
		- custom test
			- tests/fileName.sql file containing test
		- recency test
			- if there is a gap in steaming data
		- test on sources to check requirements
		- severity // warn, error
	- default materialization config
	- variables
	- tags
- schema.yml file
	- Transformation
	- contains models list, tests
		- for each models sub folder
	- models
		- table.sql file
		- defines transformation of data
	- macros // defined scripts
	- sources
		- naming, db, schema, tables
- configuration in table.sql file
	- materialized
	- alias the table name
	- schema name
	- database name
- Types of materialization
	- Table
		- fast query
		- slow to build
		- store actual data
		- drop existing table and recreate as a static table
		- data refresh with source table when running the model
	- View
		- default
		- doesn't store actual data, query logic stored
		- quick building
		- slow to query
		- data upto date with source table
	- Incremental
		- only new or updated records
		- slow build time, quick updating
		- advance config
		- unique key // list of column combined to make the key
		- incremental strategy
		- if_incremental micros
	- Ephemeral
		- temporary table, not added to db
		- do not exist as standalone objects
		- reusable logic, reusable models in other models
		- tough to debug
	- {{ config(materialized="materializedType") }}
- dbt cloud
	- connection
		- git connection
		- snowflake connection
	- create a job
		- dbt cmds
		- manual or automatic execution
- dbt Advance
	- Hooks
	  collapsed:: true
		- specific sql cmds before or after running models
		- syntax // in dbt_project.yml
		  collapsed:: true
			- on-run-end // for all models
			- models:   // for specific models
			  collapsed:: true
				- dir01
				  collapsed:: true
					- pre-hook
					- post-hook
		- for audit tables
	- Snapshot
	  collapsed:: true
		- Track data change over time
		  collapsed:: true
			- slowly changing dimensions
		- snapshots directory
		- snapshots/snapshot01.sql
		- generally for sources
	- Sources
	  collapsed:: true
		- data tables on which X'mations can run
	- Macros
	  collapsed:: true
		- Snipped of sql + ginga
		  collapsed:: true
			- as functions
		- make code clean / readable
		- operations
		  collapsed:: true
			- e.g. pause / suspend warehouse
		- Macros
	- Continuous Integration (CI) with GitHub
	  collapsed:: true
		- dbt cloud => Integration
		- CI jobs
		  collapsed:: true
			- Trigger => Webhook
			- After every pull request of github
	- Target
	  collapsed:: true
		- where the models are stored after execution
	- logs
	- seeds
	  collapsed:: true
		- static table, reference table
- Best practices
	- Environments
		- Managing environments depend upon the application
		- Production environment
		- Test environment
			- for testing use testing credentials / testing schema in project.yml
		- staging (only using view), intermediate, marts, elementary [[*]]
	- Style guide
		- CTE on top of models // common table expression
	- tags
		- tags on models
		- e.g. hourly, weekly, nightly
		- one tag or multiple tags allowed
	- limiting data
		- testing on small set of data
		- locally testing using if(target.name)
			- target.name is different for dbt cloud and local
- dbt snowflake
	- staging tables // source => staging tables
	- intermediate table // x'mation
	- tests / validation rules for each models
	- mart // departments / for team => for BI
	- elementary schema.dbt run result // dbt test / models log
	- data rock // dbt snowflake alerts
	- running model
		- github repo update => concourse pipeline => run model
		- manual concourse trigger
	- DBT Core // computing
		- Running on kubernetics