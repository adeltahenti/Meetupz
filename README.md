# My Application

> Install globaly loopback-cli.

```bash
npm i -g loopback-cli
```

> When you use GitHub, catch password in git

```bash
git config --global credential.helper wincred
```

# Installation

> Create App

```bash
lb
```

> and chose your configuration (easy)

## Run Application

```bash
node .
```

## Use MongoDB as Database Source

* Install MongogoDB Connector

```bash
npm i loopback-connector-mongodb
```

* Connect MongoDB

```bash
lb datasource mongoDS --connector mongoDB
```

> and chose the necessary options (easy)

* In the server directory, open datasources file,change mongoDS to db and delete what's on it

## Create Model

```bash
lb model
```

* Enter model name
* Select source
* Use PersistedModel as model's base class
* Expose model via REST API => Yes
* Click Enter for custom plural form
* Chose common model
* Properties
  * name as string, required or not, and leave blank for default
  * another property
  * and so also on

## Authentication

```bash
lb acl
```

* Chose a model
* Select all methods and properties
* All the roles
* Any unauthenticated user
* Explicitly deny acces

## Create User

* Create a user in _http://localhost:3000/explorer/#!/User/User_create_
* Login in _http://localhost:3000/explorer/#!/User/User_login_ (in credentials)
* To get access, copy id, and paste it in access token

## Set to only show model for all users whithout authentication

* In meetup.json file (common/models), clear acls array
* Stop the server, and

```bash
lb acl
```

* ...
* Change all the roles in write only
* ...
