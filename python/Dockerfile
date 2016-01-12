# Use ubuntu 14.04 as main image
FROM ubuntu:14.04

RUN echo "deb http://http.debian.net/debian jessie-backports main" | \
tee -a /etc/apt/sources.list

# Install dependencies
RUN apt-get clean && apt-get update
RUN apt-get install -y --force-yes build-essential python-pip python-dev \
    libjpeg-dev libfreetype6 libfreetype6-dev \
    zlib1g-dev gettext libmysqlclient-dev wget \
    libcurl4-openssl-dev libssl-dev libffi-dev sqlite3 libpq-dev libgrpc-dev xvfb xorg \
    fontconfig libfontconfig1 libpng12-0 zlib1g libjpeg-turbo8 libssl1.0.0 libx11-6 \
    libxext6 libxrender1 xfonts-base xfonts-75dpi libstdc++6 libc6

# Install wkhtmltopdf
RUN wget http://download.gna.org/wkhtmltopdf/0.12/0.12.2.1/wkhtmltox-0.12.2.1_linux-trusty-amd64.deb
RUN dpkg -i wkhtmltox-0.12.2.1_linux-trusty-amd64.deb

RUN printf '#!/bin/bash\nxvfb-run -a --server-args="-screen 0, 1024x768x24" /usr/bin/wkhtmltopdf $*' > /usr/bin/wkhtmltopdf.sh
RUN chmod a+x /usr/bin/wkhtmltopdf.sh
