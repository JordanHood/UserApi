[![Coverage Status](https://coveralls.io/repos/github/JordanHood/UserApi/badge.svg?branch=master)](https://coveralls.io/github/JordanHood/UserApi?branch=master)
[![CircleCI](https://circleci.com/gh/JordanHood/UserApi.svg?style=svg)](https://circleci.com/gh/JordanHood/UserApi)


[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/JordanHood/UserApi/blob/master)

# Node.js User API
An API to manage a user persistence layer

## Implementation

* The API exposes a user model with the following properties: id, email, forename, surname, date created
* The following endpoints are exposed: create, read, update, delete
* Can be consumed using Google Chrome's Postman. See repo for User_API.postman_collection file, which can be imported by Postman
* Input is validated and sanitised with sequalize's build in validation

## Installation
1. Install node version `v6.9.4`
2. App dependencies - `npm install`
3. Install [PostGres](https://www.postgresql.org/) - to allow user data to be persisted the app requires a connection to an instance of PostGres SQL. The local connection string is specified in the config.js file.
4. ensure that postgres is running `brew services start postgresql` if on mac os
4. run `createuser -P user_name` replacing `user_name` with your current user name
5. run `createdb db_name` replacing `db_name` with your current user name

## Usage
1. To start the Node.js server run `npm start`
On startup the app will create a users table and insert some users read from `scripts/baseData.json` to use for storing, reading, writing, and deleting 'user' information

## Tests

* Unit tests are run with [Mocha](https://mochajs.org/) which can run with `npm run test:coverage`.
* Linting is run using [StandardJs](http://standardjs.com/) which can be run with `npm run lint`.

## Documentation
Once the server is running, the api is documented using swagger, which can be accessed by going to `http://localhost:3500/`
