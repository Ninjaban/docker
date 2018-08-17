FROM ruby

RUN apt-get update && \
    apt-get install -y sqlite3 nodejs && \
    gem install rails && \
    mkdir -v --parents /opt/app

COPY /usr/local/bundle/bin/rails /opt/app
WORKDIR /opt/app
