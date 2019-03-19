FROM ubuntu:latest

RUN apt-get -y update && apt-get -y upgrade
RUN apt-get install -y openssh-server \
ca-certificates \
postfix \
tzdata \
curl

RUN curl https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh | bash

EXPOSE 80 
EXPOSE 443
EXPOSE 22

RUN service ssh restart

RUN EXTERNAL_URL="https://gitlab.example.com" apt-get install -y gitlab-ce
RUN /opt/gitlab/embedded/bin/runsvdir-start &

ENTRYPOINT gitlab-ctl reconfigure
