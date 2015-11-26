# Use ubuntu 14.04 as main image
FROM ubuntu:14.04

RUN echo "deb http://http.debian.net/debian jessie-backports main" | \
tee -a /etc/apt/sources.list

# Install dependencies
RUN apt-get clean && apt-get update
RUN apt-get install -y --force-yes build-essential python-pip python-dev \
    libjpeg-dev libfreetype6 libfreetype6-dev \
    zlib1g-dev gettext libmysqlclient-dev \
    libcurl4-openssl-dev libssl-dev libffi-dev sqlite3 libpq-dev libgrpc-dev wkhtmltopdf xvfb xorg

RUN printf '#!/bin/bash\nnxvfb-run -a --server-args="-screen 0, 1024x768x24" /usr/bin/wkhtmltopdf $*' > /usr/bin/wkhtmltopdf.sh
RUN chmod a+x /usr/bin/wkhtmltopdf.sh
RUN ln -s /usr/bin/wkhtmltopdf.sh /usr/local/bin/wkhtmltopdf