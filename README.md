# NodeGoat

Being lightweight, fast, and scalable, Node.js is becoming a widely adopted platform for developing web applications. This project provides an environment to learn how OWASP Top 10 security risks apply to web applications developed using Node.js and how to effectively address them.

## Getting Started
OWASP Top 10 for Node.js web applications: 

### Know it! 
[Tutorial Guide](http://nodegoat.herokuapp.com/tutorial) explaining how each of the OWASP Top 10 vulnerabilities can manifest in Node.js web apps and how to prevent it.

### Do it!
[A Vulnerable Node.js App for Ninjas](http://nodegoat.herokuapp.com/) to exploit, toast, and fix. You may like to [set up your own copy](#how-to-setup-your-copy-of-nodegoat) of the app to fix and test vulnerabilities. Hint: Look for comments in the source code.
##### Default user accounts
The database comes pre-populated with these user accounts created as part of the seed data -
* Admin Account - u:admin p:Admin_123
* User Accounts (u:user1 p:User1_123), (u:user2 p:User2_123)
* New users can also be added using the sign-up page.

## How to Setup Your Copy of NodeGoat

### OPTION 1 - One click install on Heroku
The the quickest way to get running with NodeGoat is to click the button below to deploy it on Heroku.

Even though it is not necessary, it is recommended that you fork this repository and deploy the forked repo.
This would allow you to fix the OWASP Top 10 vulnerabilities demonstarted in the app in your fork and deploy it on heroku mutiple times.

[![Deploy](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy)

This Heroku instance uses Free ($0/month) node server and MongoLab add-on.

### OPTION 2 - Run NodeGoat on your machine

If you do not wish to run NodeGoat on Heroku, please follow these steps to setup and run it locally - 
* Install [Node.js](http://nodejs.org/) - NodeGoat requires Node v0.10 or above

* Clone the github repository
```
git clone https://github.com/weboracle/NodeGoat/NodeGoat.git
```

* Install node modules
```
npm install
``` 

* Create Mongo DB: 
    You can create a remote MongoDB instance or use local mongod installation
    * A. Using Remote MongoDB
        * Create a sandbox mongoDB instance (free) at [MongoLab](https://mongolab.com/plans/pricing/)
        * Create a new database. 
        * Create a user.
        * Update the `db` property in file `config/env/development.js` to reflect your DB setup. (in format: `mongodb://<username>:<password>@<databasename>`)
    * OR B.Using local MongoDB 
        * If using local Mongo DB instance, start [mongod](http://docs.mongodb.org/manual/reference/program/mongod/#bin.mongod). 
        * Update the `db` property in file `config/env/development.js` to reflect your DB setup. (in format: `mongodb://localhost:27017/<databasename>`)

* Populate MongoDB with seed data required for the app
    * Run grunt task below to populate the DB with seed data required for the application. Pass the desired environment as argument. If not passed, "development" is the default:
```
grunt db-reset:development
```
* Start server, this starts the NodeGoat application at url [http://localhost:4000/](http://localhost:4000/)
```
npm start
```
#### Customizing the Default Application Configuration
The default application settings (database url, http port, etc.) can be changed by updating the [config file] (https://github.com/OWASP/NodejsGoat/blob/master/config/env/all.js).


## License
Code licensed under the [Apache License v2.0.](http://www.apache.org/licenses/LICENSE-2.0)
