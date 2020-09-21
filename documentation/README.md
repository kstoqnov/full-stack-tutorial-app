# env file client
PORT=8081

# Overview

– App is the container that has Router & navbar.
– There are 3 items using React hooks: TutorialsList, Tutorial, AddTutorial.
– http-common.js initializes axios with HTTP base Url and headers.
– TutorialService has functions for sending HTTP requests to the Apis.
– .env configures port for this React Hooks CRUD App.

These are APIs that Node.js Express App will export:

Methods	  Urls	                    Actions

GET	    api/tutorials	            get all Tutorials
GET	    api/tutorials/:id	        get Tutorial by id
POST	api/tutorials	            add new Tutorial
PUT	    api/tutorials/:id	        update Tutorial by id
DELETE	api/tutorials/:id	        remove Tutorial by id
DELETE	api/tutorials	            remove all Tutorials
GET	    api/tutorials?title=[t]	    find all Tutorials which title contains 't'

# Configure PostgreSQL database & Sequelize app/config

First five parameters are for PostgreSQL connection.
pool is optional, it will be used for Sequelize connection pool configuration:

max: maximum number of connection in pool
min: minimum number of connection in pool
idle: maximum time, in milliseconds, that a connection can be idle before being released
acquire: maximum time, in milliseconds, that pool will try to get connection before throwing error


# Sequelize 
create a new Tutorial: create(object)
find a Tutorial by id: findByPk(id)
get all Tutorials: findAll()
update a Tutorial by id: update(data, where: { id: id })
remove a Tutorial: destroy(where: { id: id })
remove all Tutorials: destroy(where: {})
find all Tutorials by title: findAll({ where: { title: ... } })

# Controller app/controllers folder

create
findAll
findOne
update
delete
deleteAll
findAllPublished

# Routes

/api/tutorials: GET, POST, DELETE
/api/tutorials/:id: GET, PUT, DELETE
/api/tutorials/published: GET

# Data Service services/TutorialService.js

The service exports CRUD functions and finder method:

CREATE: create
RETRIEVE: getAll, get
UPDATE: update
DELETE: remove, removeAll
FINDER: findByTitle