FROM python:3.9.2

SHELL ["/bin/bash", "-c"]

# Make a non root user
RUN adduser --disabled-password --gecos '' app && \
    # System deps
    apt update -y && \
    apt upgrade -y && \
    apt install -y \
    libpq-dev postgresql postgresql-contrib python-virtualenv musl-dev python3-dev sqlite3 libsqlite3-dev && \
    # Create the root structure
    mkdir /var/www /var/log/app

# We only want to work inside the code folder now
WORKDIR /var/www

# Grab dependencies before the code
COPY requirements.txt /var/www

# Change owner to non root
RUN chown -R app:app /var/www /var/log/app && \
    virtualenv -p /usr/local/bin/python /virtualenv && \
    chown -R app:app /virtualenv

# do everything as non root
USER app

RUN touch /var/log/app/app.log && \
    # Install dependencies and setup permissions
    source /virtualenv/bin/activate && \
    pip install -r /var/www/requirements.txt
