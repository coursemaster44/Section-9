# Section-9

# Section-9-Creating-Sample-App-With-CRUD-Functionality
# 1-postman-install-lab

**Step 1.Open www.postman.com/downloads/**
- Click on Download the App

**Step 2.Unzip the Downloaded file Postman-xxx.zip**

**Step 3.Move Postman application to Application folder**

**Step 4.Open Postman tool now and see the Interface**

# End of lab

# 2-JSONsting-onject-concepts-lab

**Step 1.Open terminal in Visual Studio code**
- Run the following commands-
```sh
$ mkdir test-app
$ cd test-app
$ npm init -y
$ cp ../sample-node-app/app.js .
$ npm i express
```
**Step 2.Open Postman tool>Collections>New Collection**
- Give name - test-app
Click on Create

**Step 3.Click on test-app ...>Add request**
- Give name - test

**Step 4.Click on test to Modify**
- change request to POST 
- enter URL - http://localhost:3000/test
- Body>raw>change text to JSON
{
   "name"  : "Amit"
   "place" : "Delhi"

}

Click on Send

**Step 5.Type $ node app.js**
- Click Send in Postman

# 3-env-variables-lab
**Step 1.Open terminal in Visual Studio code**
- Run the following commands-
```sh
$ mkdir crud-app
$ cd crud-app/
$ cp ../sample-node-app/ .
$ cp -r ../sample-node-app/ .
$ npm install
$ npm i env-cmd
$ node app.js
$ touch .env.dev
  DEPLOYMENT_ENV = dev
  AWS_REGION = ap-south-1
  PORT = 3000
$ node app.js
$ clear
$ ./node_modules/.bin/env-cmd -f ./.env.dev node app.js
```
# End of lab

# 4-env-variables-about-page-and-aws-sdk-lab

**Step 1.Open terminal in Visual Studio code**
Run the following commands-
$ ./node_modules/.bin/env-cmd -f ./.env.dev node app.js

**Step 2.Open browser and type localhost:3000**
- check for the changes

**Step 3. Go back to Visual Studio code**
-Type following to create .env.prod
```
$ touch .env.prod
$ mkdir controllers
$ cd controllers
$ touch curdcontroller.js
$ cd crud-app/
$ npm i aws-sdk
```
# End of Lab

# 5- curdcontroller-1-lab
**Open terminal in Visual Studio code and Follow the video**

# 6 -curdcontroller-lab
**Open terminal in Visual Studio code**
Run the following commands-
```
$ ./node_modules/.bin/env-cmd -f ./.env.dev node app.js
```

# End of lab
