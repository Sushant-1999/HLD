# NoSQL  ?

1) Structure 
	* NoSql works on Unstructured data. Not Only SQL.
	* Key Value DB, Document DB, Column Wise DB, Graph DB 4 Types of DBs comes in Unstructured. 
	* Key Value is Simplest NoSQL DB. Here we are having Key , Value : Value can be string, integer, json, structure so its like Opaque. We can't query based on Value but we can Search based on Key. 
	* Document DB - It also has Key and Value . But its value can be JSON, XML.
	* What is diff between Key Value DB and Document DB ? 
		* So, in Document DB we can query based on Key as well as based on Value as well but same is not applicable to Key Value DB as Value is Opaque in it. 
		* So, MongoDB is a Document DB. 
		* Columnar DB - 
		* Graph DB - Data is stored in Node and Edge Format . 
		

2) Nature 

	* Distributed in Nature.

3) Scaling 

	* Horizontal Scaling
	* If data is growing fast can add any number of nodes and store the user's data. It is growing Horizontal.

4) Property 

	* It is not following ACID. It is following BASE. 
	* BAsically Avaialable. Safe State and Eventual Consistency. 
	* Basically Available - Highly Available DB. As data is stored in distributed manner. Any node is down other nodes can server the Requests as it was distributed in nature.
	* Safe State - state can be chagne. State of data can be change without interaction itself. They update themselves.
	* Eventual Consistency - If repeated query after some time we might get updated data, latest data once they sync up they will update themselves. 
	* It does not follow ACID Properties. 



5) When to use SQL and when to use NoSQL ? 

	* If we want flexible query functionality then we need SQL For that. Nosql does not support flexible query. Basic query search nosql gives. SQL gives flexibility in queries. 
	* If data is kind of Relational natures like too many dependency, relational data. 
	* In NoSQL generally data is not tightly depend on each other. 
	* If lot of hierarchy is there then SQL
	* Data Integrity - follows ACID then SQL, can;t loose consistency in database, can't afford then only way is SQL. 
	* Data Integrity, Consistency is farmost required.
	* NoSQL is developed to handle Big Data , dynamic in nature, Millions and Billions of data, if loose some data no impact then go for NoSQL. 
	* Avalability - If we want high availability and high performance and with some inconsistency then we have to go for NoSQL. As it is distributed in nature it will be hightly avaialble and search capability is very very high in nature.
	 
