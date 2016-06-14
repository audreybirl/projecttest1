# projecttest1
AngularJs -> Workshop Part I

## Project Test 1 - AngularJS boiler plate

This project includes the use of following 
	 * Node
	 * Bower
	 * Gulp
	 * MongoDb (Connects to an api that uses)
	 * Sails

### Steps to run this project
 
1. Install node from here http://nodejs.org can also use nvm to swap between versions of Node https://github.com/creationix/nvm 

2. Download and run MongoDb from here https://www.mongodb.org/downloads
	
	Create a testtable and add a few records to it
	```
	use sailsDb

	db.testtable.insert( { firstname: 'Audrey', lastname: 'Bennouar' } );

	db.testtable.find({}); //list all added records

	Show dbs
	show collections
	```

3. Install sails <br>
   Create sails project <br>
	mkdir sails <br>
	cd sails <br>
	sudo npm -g install sails <br>
	sails new testProject <br>

   Lift the server
   	sails lift <br>
    Go to http://localhost:1337/ <br>
    Connect to MongoDb <br>
    cd testProject <br>
    npm install sails-mongo --save <br>
    cd config <br>
    vi connections.js <br>
    Add the following code <br>

	```
    someMongodbServer: {
	    adapter: 'sails-mongo',
	    host: 'localhost',
	    port: 27017,
	    // user: 'username',
	    // password: 'password',
	    database: 'sailsDb'
	  },
	```
	vi models.js add the following

	```
		module.exports.models = = {
			connection: ‘someMongodbServer’
		};
	```
	sails generate api testTable <br>
	sails lift <br>
		 Choose safe 1 <br>

	Test the api is bringing back data go to http://localhost:1337/testtable/ <br>
	Should list the records you added in step 2 above

4. Do an npm install & bower install in the projecttest1 directory and run gulp



