# Geographic Question-Answering System for Hindi Language

Code Description:
-----------------

	*rule.py :	Program to process the input query (present in _hindiQuery.txt_) through a set of rules and transform it to a predicate of property-NER pair. This program determines the slots to be filled in the PostgreSQL Query.

	*db_interface.py :	Program to convert the query generated by rule.py to a PostgreSQL query, and fetch the result from the database. The program displays the result in Hindi using Google Translate API.	

	*main.py :	Main Program which executes all the required codes in squence. This program:
		1.	Reads the input query from _hindiQuery.txt_	
		2.	Executes _rule.py_ to generate the intermediate query, and stores it in _query_info.txt_.
		3.	Executes _db_interface.py_ which reads the intermediate query and based on the property, executes a specific PostgreSQL query to fetch the result.


Instructions:
--------------

###1.	Setup PostgreSQL database:
	*Install PostgreSQL
	*Install the extension PostGIS
	CREATE EXTENSION postgis;
	CREATE EXTENSION postgis_topology;
	*Import the database from db/create_db.sql
	Note:	Modify the paths of all .csv files in the last six lines of db/create_db.sql to the absolute system paths of the files.

###2.	Install necessary Python Libraries:
	*Install Google API Python Client Library
	pip install google-api-python-client
	*Install PostgreSQL+Python 
	pip install psycopg2
	