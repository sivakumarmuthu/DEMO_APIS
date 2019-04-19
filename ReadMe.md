Prerequisites:
1) Anypoint studio
2) MySQL 

step 1:

set up the MYSQL local version server and run the sql scripts for creating necessary tables
https://github.com/sivakumarmuthu/DEMO_APIS/blob/master/Sql/SQL_SCRIPTS.txt

This demo assumes the following are the DB connection details and DB is started.

username:root
password:
host:localhost
port:3306.


If the above details are not correct, then this needs to be updated in mule common config DB connector.

step 2:

->Download the Mule Deployable Archive from https://github.com/sivakumarmuthu/DEMO_APIS/blob/master/DeployArchive/sys-person-contact-info.zip

->Open Anypoint studio and import the deployable arhive using Anypoint Menu,
     File->Import->Anypoint Studio generated Deployable Archive.

-> This should import all the code and the sql jar into workspace. If sql jar is missing configure it in build path.
 
-> open api.xml file in Anypoint studio and right click and run.

-> If successfully started it should open an API console in http://127.0.0.1:8081/api/console/

step 3:

-> Execute POST: http://127.0.0.1:8081/api/persons to create persons in DB. This will create one or more persons as specified in the request.
   API will return the unique Id for persons created which can be used to updtate in next steps
-> Execute GET: http://127.0.0.1:8081/api/persons to fetch persons from DB. copy the response in notepad
-> Execute PUT: http://127.0.0.1:8081/api/persons by giving the response copied in previous step and modify few attributes.
-> Execute DELETE: http://127.0.0.1:8081/api/persons to delete persons from DB. It needs the personIds in array to delete.

The sample data for APIs are avaialble as example. Please make use of them




