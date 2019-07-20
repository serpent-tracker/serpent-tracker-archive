# Serpent Tracker Microservices
The code for all services of serpent tracker

# Running Application

## Setup
Below are the different steps for setup of the application.

### Create A Secure Secret Key
You will need a secure key to run in production below are the steps to create a secure one.
```
import binascii
import os
binascii.hexlify(os.urandom(24))
```
Exit the shell and then set it as a ENV var where deploying:

`export SECRET_KEY=XXX`

## Run
TODO



# Running Tests
**Ensure you set REACT_APP_USERS_SERVICE_URL=http://localhost**

Tests can be ran with `sh test.sh`

## Individual Tests

### Client
`docker-compose up -d --build`
`docker-compose exec client npm test -- --verbose`