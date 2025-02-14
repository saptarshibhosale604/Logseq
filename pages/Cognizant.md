## .TODO A #Query
query-table:: false
query-properties:: [:block]
{{query (and [[TODO]] #A <% current page %>)}}
- ## Learnings list overview #Query
  query-sort-by:: level
  query-table:: true
  query-sort-desc:: true
  collapsed:: true
  {{query (page-property type)}}
- ## Learning list deep dive #Query
  query-table:: false
  collapsed:: true
  {{query (and (page-property level) (or [[Working]] [[Architecture]] [[Intro]]))}}
-
- [[Cognizant Contact]]
  collapsed:: true
	- Swati Khairnar (Sr. Associate - Projects AIA Data Integration)
	  collapsed:: true
		- HMH Power BI Migration
		- Project requirement
		  collapsed:: true
			- bi tool, etl tool, dvs tool, automation tool
			- jupyter, informatica
	- M, Kanagasundaram (Sr. Associate - Projects AIA Data Indst)
	  collapsed:: true
		- HMH
	- Patil, Dipali (Senior Project Manager - AIA Data Integration)
	  collapsed:: true
		- HMH Marklogic
	- Nathan, Metilda (Sr. Associate - Projects AIA ModernDataEngineering)
	  collapsed:: true
		- HMH Marklogic
	- Mishra, Tanuj (Associate - AIA ModernBI Indst)
	  collapsed:: true
		- HMH MDM
	- Babu, Mukhil (Programmer Analyst - AIA Data Indst)
	  collapsed:: true
		- HMH RevStream / IT Finance
	- Palepu, Kasuraju (Associate - AIA Data Indst)
	  collapsed:: true
		- HMH IBS
	- Bhosale, Saptarshi Suresh (Programmer Analyst AIA AIML)
- [[Project]]
	- [[HMH-IT-AMS]]
	- [[IBS]]
- [[Learning]]
	- [[Git]]
	- [[I3WM]]
	- [[Power BI]]
	- [[Informatica Cloud]]
	- [[Langchain]]
	- [[SQL]]
	- [[Python]]
	- [[DBT]]
	- [[Snowflake]]
	- [[AWS]]
	  id:: 67aed2b9-dcaf-485f-95be-45f7e7511582
		- [[Data storage]] S3, Redshift, Lake Formation
		- [[Data Transformation]] Kinesis, Firehose, Glue, Athena, Lambda
		- [[Data Log]] CloudWatch, CloudTrail
	- [[Terraform]] // Infrastructure as a code
	- [[Kubernetes]] // container
	- [[Dockers]] // container
	- [[Concourse]] // CI CD
	- Not done
	  collapsed:: true
		- Jenkins // CI CD
		- Tablau // data visualization
	- AWS Data Practitioner
- Other
	- TODO [#A] Build interview introduction
	  :LOGBOOK:
	  CLOCK: [2025-02-13 Thu 19:33:43]--[2025-02-13 Thu 19:33:44] =>  00:00:01
	  CLOCK: [2025-02-14 Fri 10:51:50]--[2025-02-14 Fri 10:51:51] =>  00:00:01
	  :END:
	- TODO [#C] HMH IBS Project Architecture
	- TODO [#A] process of solving ticket