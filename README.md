# My Data Studios - MEAN 4+ Seed Project

This is a starter project for setting up a MEAN Stack Development environment. 

![mean](./src/assets/images/meanstack-image.png)

## Benefits of using the MEAN Stack

* MongoDB: It is the open-source, free, cross-platform database for JavaScript. It uses JSON document-oriented style for all the data representation. The logic behind choosing MongoDB is that it restricts us to just one language-JavaScript for the whole application development.
* ExpressJS : Express.js is one of the most vital tools for developing effective mobile and web applications. It is the minimal framework for web development using Node.js. For server-side development, Node.js is essential and Express.js helps to publish the app on our website. It offers a diverse variety of features like database integration, simplified multiple routing and a template engines.
* Angular: It is a front-end framework that extends HTML with many attributes. It is used in developing client-side applications with modular code and a data binding User Interface. It is absolutely perfect for developing (SPAs) Single Page Applications.
* Node.js : Node.js is a very powerful, open source, cross-platform JavaScript-based run-time framework built on Google Chrome’s JSV8 engine. Being a completely free platform, it is used by thousands and thousands of developers around the world.

## Getting Started

Create a new directory on your workstation and initialize for git. Clone this repository and browse to the studios-mean4 project directory for the remaining commands below. Make sure you have angular and node installed and check using the following commands. Other components can be installed with node package manager (npm).

```
node -v
npm -v
ng -v
```

Next run `npm install` in your project folder. 

In order for the Express server to serve the project, you need to run the build command so that it finds the distribution folder to serve the files. It will create the /dist folder.  You will have the 'N' and 'A' of the MEAN stack ready. After the build step, install express server for the 'E' part of the stack as shown below. You also install the body parser and the --save indicates saving to the package.json file as a dependency.

```
ng build

npm install express body-parser --save 

```

See the server.js file for configuration of the express server. This file will have the entry for the API file that interacts with MongoDB. The port setting is indicated. Unlike using ng serve for angular apps, the express server listens on port 3000 by default. 

## Setting up mongoDB

The instructions below assume a Windows environment for locally hosted mongodb service.

[Optional cloud hosting of mongo database at mLabs](https://mlab.com/)
> Note you may choose to set up a hosted mongodb server if you are unable to install on your personal workstation.

Mongo assumes your databases are in a root folder of \data.

```
md \data\db

Start Mongo
"C:\Program Files\MongoDB\Server\3.6\bin\mongod.exe"

```
Verify mongo is running by seeing something like:
```
[initandlisten] waiting for connections on port 27017
```
Connect to mongoDB
```
"C:\Program Files\MongoDB\Server\3.6\bin\mongo.exe"
```
This commands opens up the shell. Create a database, collection and insert a record into the collection.

```
"C:\Program Files\MongoDB\Server\3.6\bin\mongo.exe"
> use mean
> db.users.insert({"name":"John Doe"})
> show dbs
```
You should see your databases listed. Go back to your project folder and install mongodb with npm and save as a dependency.
```
npm install mongodb --save
```
The connection string for this will be in the `api.js` file located in the server\routes folder. Other settings are there as well. If using mLabs, a different connection would be provided.  Now you have the 'M' in the MEAN stack ready. Use node to run the application. It should say running on `localhost:3000`.
```
npm install mongodb --save
```
The application entry point for node will be `server.js`. You launch the application on your express server by running:
```
node server
```

Browse to `localhost:3000/api/users` to see the database mongo record in JSON format.

Good luck!  :muscle: :octocat:
