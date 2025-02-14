- Ticket types
	- user access, permission
	- Resource issue
		- file not available
		- timeout
		- resource cpu limit exceeds
	- problem due to git file change
		- DAPR ticket, PR (Pull request), rollback to previous version, re run the file
	- Full refresh
- Manual task
	- jira => production support schedule task // list of manual tasks
	- drop older partitions from s3 for Athena #AWS
	  collapsed:: true
		- production support daily tasks
	- permission access end date checking
	  collapsed:: true
		- daily or weekly
		- group => list of users
		- principle // roles
		- lambda *lake formation rules* // for updating the rules from the prod permission rules.csv
		  collapsed:: true
			- dapr ticket, dapr branch, push branch
			- python code to sorting *prod permission rules.csv* contain
			- make a PR (pull request)
			- make a review request on teams / group
			- after approve merge branch
			- auto run lambda or manual run
		- service now ticket
	- hcp file from postgreSQL to snowflake, weekly task, on monday
	  collapsed:: true
		- open *connect vpn* => bedrock vpn
		- postgresql db connection => SELECT data
		- => export file fileName.csv
		- cmd => snowsql => octa // no need for bedrock vpn
		- snowsql cmd
		  collapsed:: true
			- local => staging
			- check staging@fileName.csv
			- clone table
			  collapsed:: true
				- get clone table (dummy table) row count // before loading .csv file
				- truncate clone table
				- insert .csv file to clone table
				- get clone table row count // after loading .csv file
				- checking clone table data
			- main table
			  collapsed:: true
				- get main table row count // before loading .csv file
				- truncate main table
				- insert .csv file to main table
				- get main table row count // after loading .csv file
				- checking main table data
	- posting cloud tail logs => s3 bucket // monthly task, only for prod
	  collapsed:: true
		- role types
		  collapsed:: true
			- data analytics role
			- data engineer role
			- data admin role
		- cloud trail => exporting needed data file01.json file local
		- file01.json => s3 =>
		- check from athena
	- postgreSQL (RDS) => .csv file => // monthly task
	  collapsed:: true
		- => s3 // bedrock vpn
	- update tf workspace version
	  collapsed:: true
		- quarterly
		- make dapr ticket
		- update tf version
	- Automation possible for this manual task
- Support tickets sources
  collapsed:: true
	- Pager duty tickets, Incident tool
		- Failed lambda functions
		- diff environment
			- Prod // high priority
		- Data dog
			- DBT For logging
	- HMH service now tickets, access
		- Ticket raised // high priority
		- Github
			- Repo
			- Granting access on table
			- lambda function check access file and do that
	- atlassian Jira tickets, customer support
		- if not ticket created, create the ticket
- High level tickets
  collapsed:: true
	- solve from ours side
	- pass the ticket to team members if not solvable
	- take help from others
	- redirect to the respective team
- Best practices
  collapsed:: true
	- Priority wise ticket solving
	- multi high priority tickets
		- start serially with most priority ticket
- Ticket sources
	- Tablau ticket
	- Bedrock team