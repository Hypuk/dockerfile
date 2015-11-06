# Use ubuntu 14.04 as main image
FROM ubuntu:14.04

# Install dependencies
RUN apt-get clean && apt-get update
RUN apt-get install -y build-essential python-pip python-dev \
    libjpeg-dev libfreetype6 libfreetype6-dev \
    zlib1g-dev gettext libmysqlclient-dev \
    libcurl4-openssl-dev libssl-dev libffi-dev sqlite3 libpq-dev libgrpc-dev
