# quizapp
a Word Quiz flask app 

##Notes for the Quiz App

The purpose of this app is to teach full stack web development.  quizapp is a Flask application (written in Python 3) which demonstrates the use of MongoDB with pymongo.  In order to run this code on your local machine, follow these steps:

* clone the repo

git clone <>

* set up a virtual environment

`virtualenv -p python3 qenv`

* start the virtualenv

`. qenv/bin/activate`

* upgrade pip immediately to avoid installation errors

`pip install --upgrade pip`

* install required packages:

`pip install -r requirements.txt`

You'll need to create a `secure.py` file in order for this app to run.

Here is a sample `secure.py` file.

APP_SECRET_KEY = "whoa this is a 53crEt K3Y!!!"

MONGO_USERNAME = "dev"
MONGO_PASSWORD = "really secure passw0rd"





Next, we need to set up the users inside MongoDB.

at the prompt, run this:

mongo

> use admin
db.createUser(  
  {
    user: "admin1",
    pwd: "some other re@lly secure passw0rd",
    roles: [ { role: "userAdminAnyDatabase", db: "admin" } ]
  }
)

use aprender

db.createUser(
  {
    user: "dev",
    pwd: "really secure passw0rd",
    roles: [ { role: "readWrite", db: "aprender" },]
  }
)


* in a new terminal window, start a MongoDB instance

`mongod`

* import the example data!
(edit this command to include the proper filepath)

`mongoimport --db aprender --collection thingstolearn --type csv --headerline --file /file/path/to/the/CSV/quizwords.csv`

* run the db setup file (ONLY ONCE)

`python dbsetup.py`

* run the app

`python app.py`

If successful, you should then see a message such as:

```
 * Running on http://0.0.0.0:8080/ (Press CTRL+C to quit)
 * Restarting with stat
 * Debugger is active!
 * Debugger pin code: (numbers)
```


First, go to:

http://0.0.0.0:8080/demo

This is just a plain HTMl page.  Can you find the files inside /templates which you need to edit in order to modify this page?  
