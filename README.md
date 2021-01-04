## demo app - developing with Docker

This demo app shows a simple user profile app set up using 
- index.html with pure js and css styles
- nodejs backend with express module
- mongodb for data storage

All components are docker-based

### This app is based on youtube video: https://www.youtube.com/watch?v=3c-iBn73dDE
Git Link: https://gitlab.com/nanuchi/techworld-js-docker-demo-app

#### Originally Node.js application in the above app had three components: 
a) Front End App in Node.js: This would run locally. Node JS to be installed on laptop
b) Mongo DB - Runs in a container
c) Mongo DB Express (A front end to access the mongo DB, like SQLDevloper): Runs in a container

### Changes I made: 
I dockerized the nodejs app as well. To run the app, just download the code and run following command

    docker-compose -f docker-compose.yaml up

This will create three containers.
### With Docker

#### To start the application - with Docker Compose

Step 1: start mongodb and mongo-express

    docker-compose -f docker-compose.yaml up

_Note:This will create following three containers
CONTAINER ID   IMAGE                                     COMMAND                  CREATED          STATUS          PORTS                      NAMES
6092f677e0dc   mongo                                     "docker-entrypoint.s…"   37 seconds ago   Up 35 seconds   0.0.0.0:27017->27017/tcp   techworld-js-docker-demo-app-master_mongodb_1
d414400695c2   mongo-express                             "tini -- /docker-ent…"   38 seconds ago   Up 36 seconds   0.0.0.0:8080->8081/tcp     techworld-js-docker-demo-app-master_mongo-express_1
a09a0588770e   techworld-js-docker-demo-app-master_app   "docker-entrypoint.s…"   38 seconds ago   Up 36 seconds   0.0.0.0:3000->3000/tcp     mynodeapp

Step 2: open mongo-express from browser

    http://localhost:8081

Step 3: Access you nodejs application UI from browser

    http://localhost:3000 
