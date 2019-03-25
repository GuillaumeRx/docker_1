FROM ruby:latest

RUN apt-get -y update && apt-get -y upgrade
RUN apt-get -y install sqlite3 \
mysql-client \
tzdata

RUN gem install rails

RUN mkdir -p /opt/app

WORKDIR /opt/app

ONBUILD ADD app/ opt/app
ONBUILD RUN bundle install

ONBUILD RUN rails db:migrate
ONBUILD RUN rails db:seed

EXPOSE 3000

#docker build -t ft_rails:on-build .