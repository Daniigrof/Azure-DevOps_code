This program uses mongodb Database and set  DB-name DB-root-user & DB-root-password as a ENV's in the docker-compose.yml
------------
If you not use the ENV's for mongo (any security issues),
You need to run mongo image and create new username & password and DB name 
Do it with the next commands 
It necessary to backend service that can connect to mongo container with specific credentials

-->

docker exec -it mongo bash

mongosh

use MyDB

db.createUser({ user: "Dani", pwd: "Dani3653", roles: [] })



----------------------------------------------
In case you want to build custom mongodb image,
Do it with entrypoint file
Create mongo-init.js file and set the default values for the mongodb container
In this example you set new DB with name "MyDB" and username and password.

-->

db.createUser( { user: "Dani", pwd: "Dani3653", roles: [ { role: "readWrite", db: "MyDB" } ] } );


If you want to create custom mongodb contaner - use the next Dockerfile 

-->

FROM mongo:4.4.18

COPY ./mongo-init.js /docker-entrypoint-initdb.d
