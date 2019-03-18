FROM debian:latest

RUN apt-get update \
	&& apt-get install -y wget \
	&& apt-get install -y bzip2
RUN wget https://files.teamspeak-services.com/releases/server/3.6.1/teamspeak3-server_linux_amd64-3.6.1.tar.bz2
RUN tar -xvf teamspeak3-server_linux_amd64-3.6.1.tar.bz2
RUN rm teamspeak3-server_linux_amd64-3.6.1.tar.bz2
RUN cd teamspeak3-server_linux_amd64
RUN touch .ts3server_license_accepted


EXPOSE 9987
EXPOSE 30033
EXPOSE 10011
EXPOSE 41144

CMD sh ./teamspeak3-server_linux_amd64/ts3server_minimal_runscript.sh start license_accepted=1