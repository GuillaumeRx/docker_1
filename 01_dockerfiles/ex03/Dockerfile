FROM debian:latest

RUN apt-get update
RUN apt-get install -y curl \
openssh-server \
ca-certificates \
postfix \
tzdata

RUN curl https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh | bash && apt-get -y install gitlab-ce

ENTRYPOINT service ssh start && (/opt/gitlab/embedded/bin/runsvdir-start &) && gitlab-ctl reconfigure && tail -f /dev/null

EXPOSE 80
EXPOSE 443
EXPOSE 22