# Geographic Question-Answering System for Hindi Language

##   Code Description:
-----------------
###### The following codes are present in the  _RuleBasedSystem_  directory
- __rule.py__  
Program to process the input query (present in _hindiQuery.txt_) through a set of rules and transform it to a predicate of property-NER pair. This program determines the slots to be filled in the PostgreSQL query

- __db_interface.py__  
Program to convert the query generated by rule.py to a PostgreSQL query, and fetch the result from the database. The program displays the result in Hindi using Google Translate API

- __main.py__  
    Main Program which executes all the required codes in squence. This program:  
    - Reads the input query from  _hindiQuery.txt_ 	
    - Executes _rule.py_ to generate the intermediate query, and stores it in  _query_info.txt_   
    - Executes   _db_interface.py_   which reads the intermediate query and based on the property, executes a specific PostgreSQL query to fetch the result


## Instructions:
--------------

##### 1.	Setup PostgreSQL database:  
* Install PostgreSQL
* Install the extension PostGIS
```sh			
    CREATE EXTENSION postgis;
    CREATE EXTENSION postgis_topology;
```
* Import the database from db/create_db.sql
* Import all the .csv files present in _db_ directory to your database

##### 2.	Install necessary Python Libraries:
* Install Google API Python Client Library
```sh				
pip install google-api-python-client
```		
* Install PostgreSQL+Python 
```sh				
pip install psycopg2
```	

##### 3.    Execution:
* Write your question in Hindi in _RuleBasedSystem/hindiQuery.txt_
* Execute ```RuleBasedSystem/main.py```


##### 4.	Additional Instructions to install and use Hindi Wordnet:
* switch to __JHWNL_1_2__ directory
* Compile all files here:
```sh				
javac -cp JHWNL.jar:. *.java
```	
* Execute __GetSynonyms.java__ to get the list of synonyms of an input Hindi word
```sh				
java -cp JHWNL.jar:.  GetSynonyms
```	
