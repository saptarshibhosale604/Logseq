level:: 2
comment:: LLM powered application building framework
type:: framework

- Modules or components
- Model IO
  collapsed:: true
	- LLM
	  collapsed:: true
		- Text completion
		- Chat
			- System level prompt
		- multiple different services
	- Prompt templates
	  collapsed:: true
		- Passing arguments in the input message
		- Few shot prompt templates
			- Start chat with example initial 2 or more conversational messages
			- Start the flow of the chat
	- Parsing output
		- Converting string to list
		- Converting multiple types of date string to formatted date
		- Converting string to custom defined class or json format
	- Serialization
		- Saving and loading prompt
- Data connection
  collapsed:: true
	- Document loaders
		- csv, html, pdf, etc
	- Document transformation
		- Making chunks of the doc
	- Text embedding
		- text => vector
	- Vector store
	- Similarity doc retrieval
	- Multi query retrieval
	- Context compression
- Chains
  collapsed:: true
	- Simple sequential chain
		- input => [ chain01 => chain02 ] => output
		- only in series
		- only one input and one output in chains
		- can't work on chain01 output
	- Sequential chains
		- can work on chain01 output
	- router chains
		- Redirect input to most appropriate chain
- Memory
- Langchain Agents