FROM debian

ENV TS3SERVER_LICENSE=accept
RUN adduser --disabled-password --gecos "" teamspeak
RUN mkdir /opt/teamspeak
RUN chown teamspeak:teamspeak /opt/teamspeak/
RUN chmod 0770 /opt/teamspeak/
RUN apt-get update && apt install -y wget && apt install bzip2 && wget http://dl.4players.de/ts/releases/3.13.2/teamspeak3-server_linux_amd64-3.13.2.tar.bz2
RUN tar -xvf teamspeak3-server_linux_amd64-3.13.2.tar.bz2
RUN mv teamspeak3-server_linux_amd64/* /opt/teamspeak/
RUN rm -rf ~/teamspeak3-server_linux_amd64*

EXPOSE 9987/udp 10011 30033
ENV TS3SERVER_LICENSE=accept
WORKDIR /opt/teamspeak
ENTRYPOINT sh ts3server_minimal_runscript.sh
