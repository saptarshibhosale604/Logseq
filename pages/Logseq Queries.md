language:: datalog
type of language:: clojure

- preprogrammed queries
- simple queries
  collapsed:: true
	- AND
	- OR
	- NOT
	- BETWEEN
	- PROPERTY #Tried
	  id:: 67ad9a40-6ad5-447f-b172-95a24702ba0c
	  collapsed:: true
		- propertyName01:: propertyValue01
		  propertyName02:: propertyValue02
		- on first block of the page
		  :LOGBOOK:
		  CLOCK: [2025-02-13 Thu 18:51:50]
		  :END:
		- propertyValues are links
		- types
			- property // for a block and a page
			- page-property // for page only
		- [[Query]] property 
		  {{query (property os "na")}}
		- [[Query]] page property
		  query-sort-by:: page
		  query-sort-desc:: false
		  query-properties:: [:page :language :level :os]
		  collapsed:: true
		  {{query (page-property os)}}
		- [[Query]] page property, property value
		  collapsed:: true
		  {{query (page-property os "Linux")}}
		- [[Query]] page property, property value
		  query-properties:: [:page :language :level :os]
		  collapsed:: true
		  query (or (page-property os "linux") (page-property os "na"))}}r
		  {{query (page-property level)}}
			- {{function (sum: level)}}
			-
			-
			-
			-
		- {{query ()}}
		-
		-
	- .TODO
	  id:: 67ad94fb-bc50-4ecd-82af-bc96aedc7576
	  collapsed:: true
		- {{query (todo done)}}
	- PRIORITIES
- test block with properties
  language:: txt
  level:: na
  os:: na
  collapsed:: true
	- child of test block
- Advance queries
	- #+BEGIN_QUERY
	  {
	  :title [:b "Hello world #QueryAdvance"]
	  }
	  #+END_QUERY
	- #+BEGIN_QUERY
	  {
	   :title [:b "OVERDUE #QueryAdvance"]
	   :query [
	           :find (pull ?b [*])
	           :in $ ?start ?today
	           :where
	           (task ?b #{"I3WM"})
	           (?b :block/priority "A")
	          ]
	   :inputs [:-180d :today]
	   :breadcrumb-show? true
	  }
	  #+END_QUERY
- [[Query]] Testing queries
  collapsed:: true
	- {{query (and (not [[I3WM]]) [[A]])}}
	  query-table:: false
	  query-properties:: [:block]
	  :LOGBOOK:
	  CLOCK: [2025-02-13 Thu 12:26:57]--[2025-02-13 Thu 12:26:58] =>  00:00:01
	  :END:
	- {{query (and (not #i3wm) #B )}}
	- {{query (and [[I3WM]] [[DONE]] )}}
	-
	- ##
-