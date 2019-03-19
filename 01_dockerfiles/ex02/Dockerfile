FROM ruby:latest

RUN apt-get -y install sqlite3 libsqlite3-dev
RUN gem install rails

ONBUILD COPY . opt/app