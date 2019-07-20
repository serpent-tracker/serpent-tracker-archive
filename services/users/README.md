# users
Users microservice built on flask and docker with postgres db.

# Install
1. Install pipenv `pip install pipenv`
2. Install dependencies with pipenv - `pipenv install`


# Running
After installing you can now activate the env with `pipenv shell` and then run the below to start the app:

`python manage.py run`

# Docker
You can also use docker with compose for easy dev and testing:

## Bringup
`docker-compose up -d` - This hot loads on code changes.

## Running Tests
`docker-compose exec users python manage.py test`

## Running Coverage
`docker-compose exec users python manage.py cov`

## Running Flake
`docker-compose exec users flake8 project`

## DB Stuff
You can gain access to the postgres shell via `docker-compose exec users-db psql -U postgres` in local dev testing.

**Viewing Postgres Shell**
1. Connect to db - `\c users_dev`
2. List Table - `\dt`
3. Quit - `\q`

**Recreate DB**
`docker-compose exec users python manage.py recreate_db`

**Seed Database**
`docker-compose exec users python manage.py seed_db`

# CLI Menu
There is a cli menu that is reachable via `python manage.py` or `docker-compose exec users python manage.py` if running in docker setup.
 
# Migrations
`docker-compose exec users python manage.py db init`

`docker-compose exec users python manage.py db migrate`

`docker-compose exec users python manage.py db upgrade`