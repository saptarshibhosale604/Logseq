- HMH // Houghton Mifflin Harcourt
- American publisher of
	- text book,
	- instructional technology,
	- materials,
	- assessments and
	- reference works
- subdivisions within HMH projects
	- HMH IT AMS, // HMH - Information Technology - Application Maintenance and Service
	- HMH IBS,
	- HMH CMS, and
	- HMH DS
- Teams
	- SAP team,
	- SFDC team,
	- Central Database team,
	- IT Finance team,
	- Technology Solution Group (TSG), and
	- MDM team
- Points to add in cv
	- Project // explaination of 1.5 yrs
	- client name HMH
	- project MDM
	  HMH RevStream
	  HMH Marklogic support
	- project description
	- roles and responsibilities
	  5 points
- Project modules
	- IT Finance
	  collapsed:: true
		- Mukhil // HMH RevStream
			- Resume points
				- Technology stack
					- RAW
					  collapsed:: true
						- MySQL
						- PostgreSQL
						- Oracle
						- Informatica Intelligent Cloud Services (IICS)
						- Amazon Web Services (AWS)
						- Unix
						- WinScp
						- SQL Developer
						- Putty
					- Final
						- MySQL, PostgreSQL, Oracle, IICS, AWS
				- Description
				  collapsed:: true
					- RAW
					  collapsed:: true
						- HMH IT Finance, we work on Revenue data, were SAP and CDB are our sources and our downstream application is RevStream. We work on reconciling the data between SAP and CDB, if we have any data mismatchs we work on fixing the mismatch and we are using Informatica cloud jobs for both pulling the data from the sources and processing it to downstream. We support job monitoring and job failures and we work on business requests like DES, PCA, outbound files. We also support code migrations, job scheduling.
					- FINAL
					  collapsed:: true
						- The project works on revenue data, which reconciles SAP and CDB source data and sends it to the RevStream downstream application. Using Informatica cloud jobs, this ETL (Extract, Transform, Load) process is completed. The project fulfills various business requests, such as DES, PCA, and generating outbound files.
				- Responsibilities
				  collapsed:: true
					- RAW
					  collapsed:: true
						- Monitoring the jobs in Informatica Cloud.
						- Working on resolving daily data imbalances.
						- Working on critical job failures.
						- Working on incidents and service requests.
						- Performing UAT testing for new developments in lower environment.
						- Working on creating PCA files as per business request.
						- Modifying stored procedures to adapt new business requirements.
						- Worked on code migrations from lower environment to Production.
					- FINAL
					  collapsed:: true
						- Monitoring and working on job failures in Informatica Cloud.
						- Working on resolving daily data imbalances.
						- Perform UAT test for new developments in lower environment.
						- Working on creating PCA files as per business request.
						- Modify stored procedures to adapt new business requirements.
						- Work on code migrations from lower environment to Production.
		- team RevSprings / IT finance
		- Basic ticket solving
		  collapsed:: true
			- Stopping / modifying schedules
			  collapsed:: true
				- make ticket
				- informatic adimins => schedules
				- => edit schedules
			- daily report imbalance
			  collapsed:: true
				- raise ticket
				- amt, qty, records mis match
				- check tables queries
				- => send to sap team
				- same day solving
			- Data Extract Service DES job
			  collapsed:: true
				- update script id from mail => send s3 files to other team
				- run job informatica
				- check des job files in s3
				- Outbound schedules
				  collapsed:: true
					- month end
					- 2 sets // download file from s3 => send to business
					- from filezilla to sap server
			- Job failures
			  collapsed:: true
				- No expected too much failures
				- linear task flow // using in rev stream
				- task flow // very simple serial task flow
			- UAT tesing
			  collapsed:: true
				- from buisiness
			- PCA
			  collapsed:: true
				- weekly file sending
				- if record issue from business =>
				- send records again manually
			- Manual tasks
			  collapsed:: true
				- solve issue on job failures
				  collapsed:: true
					- on month end check files in S3
					- file type
					  collapsed:: true
						- type of file => no of files, ...
						- sales 3, billing 3, delivery 1, digital entitlement 1
						- x'saction, lines, events
				- month end process
				  collapsed:: true
					- schedule change // on 1st of the month
					- s3_a3 stop jobs
					- business allowed => start jobs
		- Architecture
			- Sources
				- SAP => no permanent storage => MySQL server // truncated next day
				- Central Database (CDB) => store in MySQL server // saved
			- daily incoming data from source, same data from both source
			  collapsed:: true
				- transaction table // today data
				- run table // past days data
				- history table
				  collapsed:: true
					- run table => history table // on the days of a week
					- run table => after X'mation => data downstream to RevStream // twice a week MON, WED // 1st of every month
					  collapsed:: true
						- manage and adjust/ transform the data from both sources
						- job S3_A3 listTasks01 + listTasks02
			- PostgreSQL // source, IICS // run job, MySQL // target from daily jobs ,
			- iics environment
			  collapsed:: true
				- IICS more scalability and the maintenance easier compared to the Informatica PowerCenter
				- Legacy prod // for RevSpring
				- Cert (Legacy sandbox) // for RevSpring
				- Prod
				- Dev
				- QA
			- iics server // secure agent server, run informatica jobs
			  collapsed:: true
				- source => files + files(encrypted)
				- files + files(encrypted) => archive
				- files(encrypted) => downstream, S3
			- Advance
			  collapsed:: true
				- DES requests
				- backend encryption // GPG encryption
				- ensuring consistency
			- job Run_A3 listTasks01
	- MDM  (Master Data Management)
	  collapsed:: true
		- Tanuj // HMH MDM
		  collapsed:: true
			- Resume points
				- Technology stack
					- RAW
						- MySQL
						- PostgreSQL
						- Oracle
						- Informatica Master Data Management (MDM)
						- Informatica PowerCenter (PC)
						- Informatica Intelligent Cloud Services (IICS)
						- Amazon Web Services (AWS)
						- Unix
						- WinScp
						- SQL Developer
						- Putty
					- FINAL
				- Description
				  collapsed:: true
					- RAW
					  collapsed:: true
						- MDM, we work on Master data management, where we have 3 source system SAP, SFDC, MDR and 1 target SAP. We consolidate the records from the 3 sources and generate the best golden record i.e., master data and send to SAP. During the load, if there is any data mismatch or attributes related issue, then we need to update that field and resend the data to downstream i.e.,SAP. The SAP and SFDC data are loaded on daily basis whereas MDR data loaded once in month. Apart from this, we generally support on job failures and monitoring and work on the business request like address change,relationship fields, manual queue reporting, resolving error in Customer360(IDD). We also help the business users to develop or migrate any features as per the client requirement.
					- FINAL
					  collapsed:: true
						- Key aim here in this project is to consolidate the records from SAP, SFDC, MDR these 3 sources to a target SAP. Generation of such best golden records should be clear from any mismatch or attributes related issue. The golden records are then pass to downstream where SAP and SFDC data get loaded.
				- Responsibilities
				  collapsed:: true
					- RAW
					  collapsed:: true
						- Monitoring the jobs in Informatica MDM.
						- Working on critical job failures.
						- Working on incidents and service requests.
						- Working on loading monthly MDR Data.
						- Creating business reports for monthly MDM data feed.
						- Working on Address doctor issues as per the business requirements.
						- Curating the data stats to match with the cross functional team.
						- Working on developing features if needed, to ensure the business requirements.
					- FINAL
					  collapsed:: true
						- Monitoring the jobs in Informatica MDM.
						- Working on critical job failures, incidents and service requests.
						- Working on loading monthly MDR Data.
						- Creating business reports for monthly MDM data feed.
						- Curating the data stats to match with the cross functional team.
						- Working on developing features if needed, to ensure business requirements.
		- Task
		  collapsed:: true
			- provide support
			- smooth operation of data processing jobs
			- monitor jobs
			- troubleshoot the issues in case of failure
		- Common challenges
		  collapsed:: true
			- server issues
			- incomplete dependent jobs,
			- parallel job execution,
			- and conflicts that arise when two or more inputs target the same table simultaneously
		- diagram
			- ![{991DAEAF-D466-4A50-A0A4-B64E735BC831}.png](../assets/{991DAEAF-D466-4A50-A0A4-B64E735BC831}_1738243951011_0.png)
		- postgresql // xml data => powercenter processing // xml to tabular conversion
		  collapsed:: true
			- archive db // xml data // before business logic data
			- dev, prod, test // no backup
			- mapping from each source, mapping 23 X'mation, 20 Mapplets , 123 mappings, nested mapping, 22 landing table
			- dont have any documentation
			- business logic = data quality rules
			- mdm, oracle db
			- java messaging service, JMS
			- ticket
			  collapsed:: true
				- data lost in landing table //
				- landing table to BI // problem
			- data coming
			  collapsed:: true
				- weekly, monthly, regularly
				- irregularly
		- Sources
			- SAP //
			- Salesforce (SFDC) and
			- MDR // monthly
			- => store in Oracle database
			- => various base object tables
			  collapsed:: true
				- matching and merging process
				- single, authoritative view of the data
		- Informatica PowerCenter
		  collapsed:: true
			- data cleansing
			- standardizing data formats,
			- validating entries against predefined rules, and
			- resolving duplicates
			- => staging table
	- TSG Integration (Technology Solutions Group)
	- Tools used
	  collapsed:: true
		- MySQL
		- PostgreSQL
		- Oracle
		- Informatica Master Data Management (MDM)
		- Informatica PowerCenter (PC)
		- Informatica Intelligent Cloud Services (IICS)
		- Amazon Web Services (AWS)
		- Unix
		- WinScp
		- SQL Developer
		- Putty
	- Roles
	  collapsed:: true
		- M. Kanagasundaram
		  collapsed:: true
			- Tech Lead HMH-IT-AMS project
			- expertise across all modules including
			  collapsed:: true
				- IT Finance,
				- Technology Solutions Group (TSG), and
				- Master Data Management (MDM).
			- guiding members,
			- troubleshooting complex issues, and
			- implementing best practices.
		- Babu, Mukhil
		  collapsed:: true
			- IT Finance and
			- Technology Solutions Group (TSG).
			- RevStream
		- Mishra,Tanuj
		  collapsed:: true
			- MDM integration within the HMH IT AMS project
	- Extra
		- Marklogic // call anshika regarding this work
		  collapsed:: true
			- Resume points
				- Technology stack
				  collapsed:: true
					- FINAL
					  collapsed:: true
						- NoSQL, Marklogic, REST API, MLCP
				- Description
					- RAW
					- FINAL
					  collapsed:: true
						- The project works on service textbook related content to E-learning Website from Marklogic storage. The data retrieval process is done using Rest API
				- Responsibilities
					- RAW
					- FINAL
					  collapsed:: true
						- Optimized query performance, configurations and query plans.
						- Integrated data pipelines using MarkLogic’s REST API.
		- PowerBI migration
			- | Category | Details |
			  | ---- | ---- | ---- |
			  | Company | Cognizant, Pune |
			  | Client | HMH (USA) |
			  | Tools & Technologies | Power BI |
			  | Team Size | 3 |
			  | Role | BI Tester |
			  | Duration | July 15-till date |
			- Project Description: The purpose of this project is as part of NWEA acquisition HMH wants to migrate the tenant from acquired entity to HMH.
				- Phase 1 of the program was focused on office 365 tenant to tenant migration and is currently in progress.
				- Phase 2 will be migrating Power Platform.
				- Phase 3 will be to migrate all the Power BI reports from one tenant to another.
			- Role and Responsibilities:
				- Involved in preparing the Test Plans, Test Strategy documents, Test Cases & Test Scripts based on business requirements, rules, data mapping requirements and system specifications.
				- Written Test Cases for Power BI Reports to compare Source Reports (NWEA account) with Target Reports (HMH account).
				- Involved in preparation of Requirement Traceability Matrix (RTM), Defect Report, and Weekly Status Reports, Test Readiness Review Documents, Test Summary Reports.
				- Worked with developer to fix errors or issues encountered during Validation of reports.
				- Interact and Co-ordinate with client during different levels of Testing.
				- Reviewed the test activities through daily scrum stand-up meetings.
- Daily scheduled calls, daily status call, know the process
- Back plan : tell as a back up resource
- I can manage the work
- where to direct the interview // technical side aws, cloud, snowflake, dbt
- Director mail
  collapsed:: true
	- Mayaperumal, Rajesh 
	  any update, feedback 
	  regading the project 
	  rajesh.mayaperumal@cognizant.com
	- mail01
		- Hi @Rajesh
		- M, Kanagasundaram (Cognizant) shared me your contact.
		- With the opportunity having at HMH I have prepared my resume. Can you kindly provide me with some suggestions or updates depending on the expectations from the industry.
		- I have attached my resume in this mail.
	- mail 02
		- Subject: Request for Resume Review and Suggestions
		- Hi Mayaperumal, Rajesh,
		- I hope you are doing well.
		- M, Kanagasundaram shared your contact information with me, and I am reaching out regarding the opportunity at HMH. I have prepared my resume and would greatly appreciate any suggestions or updates you might have based on the industry expectations.
		- I have attached my resume for your review. Thank you in advance for your time and assistance.
		- Best regards,
		- Saptarshi Bhosale
		- Programmer Analyst
		- +91 70580 33447
	- mail 03
		- Subject: Request for Resume Review and Suggestions
		-
		- Hi M. Kanagasundaram,
		-
		- I hope you are doing well.
		-
		- I am reaching out to seek your guidance regarding my resume as I prepare for the opportunity at HMH. I would greatly appreciate any suggestions or insights you might have based on your experience and industry expectations.
		-
		- I have attached my resume for your review. Thank you in advance for your time and assistance.
		-
		- Best regards,
		- Saptarshi Bhosale
		- Programmer Analyst
		- +91 70580 33447