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

# 7-postman-api-config

**Step 1.Open terminal in Visual Studio code**
- Run the following command to start the application
```
$ ./node_modules/.bin/env-cmd -f ./.env.dev node app.js
```

**Step 2.Open Postman Tool**
- Goto Collections>New Collection 
  - Give Name - crud-app
**Step 3.Click on crud-app>...>Add Request**
- Request name - "createTable"
- Click Save to crud-app

**Step 4.Click on crud-app>...>Add Request**
- Request name - "insertData"
- Click Save to crud-app

**Step 5.Click on crud-app>...>Add Request**
- Request name - "readData"
- Click Save to crud-app

**Step 6.Click on crud-app>...>Add Request**
- Request name - "updateData"
- Click Save to crud-app

**Step 7.Click on crud-app>...>Add Request**
- Request name - "deleteData"
- Click Save to crud-app

**Step 8.Click on crud-app>...>Add Request**
- Request name - "deleteTable"
- Click Save to crud-app

**Step 9.Click on createTable**
- Select POST from drop-down list
- Give URl---http://localhost:3000/createTable
- Select Body>raw>json>paste the following data
```sh
  {
    "TableName" : "Movies",
    "KeySchema": [       
        { "AttributeName": "year", "KeyType": "HASH"},
        { "AttributeName": "title", "KeyType": "RANGE" }
    ],
    "AttributeDefinitions": [       
        { "AttributeName": "year", "AttributeType": "N" },
        { "AttributeName": "title", "AttributeType": "S" }
    ],
    "ProvisionedThroughput": {       
        "ReadCapacityUnits": 1, 
        "WriteCapacityUnits": 1
    }
}
```
**Step 10.Click on insertData**
- Select POST from drop-down list
- Give URl---http://localhost:3000/insertData
- Select Body>raw>json>paste the following data
```sh
{
    "TableName":"Movies",
    "Item":{
        "year": 1997,
        "title": "As good as it gets",
        "info":{
            "plot": "A bigoted compulsive writer falls in love",
            "rating": 7.7
        }
    }
}
```
**Step 11.Click on readData**
- Select POST from drop-down list
- Give URl---http://localhost:3000/readData
- Select Body>raw>json>paste the following data
```sh
{
    "TableName":"Movies",
    "Key":{
        "year": 1997,
        "title": "As good as it gets",
        }
    }
```
**Step 12.Click on updateData**
- Select POST from drop-down list
- Give URl---http://localhost:3000/updateData
- Select Body>raw>json>paste the following data
```sh
{
    "TableName":"Movies",
    "Key":{
        "year": 1997,
        "title": "As good as it gets"
		
        },
		"UpdateExpresssion:"set info.rating = :r, info.plot=:p, info.actors=:a",
		"ExpressionAttribute Values":{
		":r":9.5;
		":p":Everything happens all at once.",
		":a":[Jack Nicholson","Helen Hunt"]
		
		},
		"ReturnValues":"UPDATED_NEW"
		
    }
```
**Step 13.Click on deleteItem**
- Select POST from drop-down list
- Give URl---http://localhost:3000/deleteItem
- Select Body>raw>json>paste the following data
```sh
{
    "TableName":"Movies",
    "Key":{
        "year": 1997,
        "title": "As good as it gets"
		
      },
    "ConditionExpression": "info.rating <= :val",
	"ExpressionAttributeValues":{
	":val":10
	}
}
```
**Step 14.Click on deleteTable**
- Select POST from drop-down list
- Give URl---http://localhost:3000/deleteTable
- Select Body>raw>json>paste the following data
```sh
{
    "TableName":"Movies",
}
```
# End of Lab





