# base image
FROM python:3.7.2-slim

# install netcat
RUN apt-get update && \
    apt-get -y install netcat gcc python-dev musl-dev && \
    apt-get clean


# set working directory
WORKDIR /usr/src/app

# add app
COPY . /usr/src/app

# add and install requirements
RUN pip install pipenv
RUN pipenv install $(test "$FLASK_ENV" == production || echo "--dev") --deploy --system --ignore-pipfile

# make entrypoint.sh writable
RUN chmod +x /usr/src/app/entrypoint.sh

# run server
CMD ["/usr/src/app/entrypoint.sh"]