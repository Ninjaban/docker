FROM debian

RUN apt-get update && apt-get install -y ca-certificates wget tar bzip2
RUN adduser --disabled-login --gecos "" teamspeak

EXPOSE 9987/udp
EXPOSE 30033/tcp
EXPOSE 10011/tcp

WORKDIR /home
RUN wget http://dl.4players.de/ts/releases/3.1.1/teamspeak3-server_linux_amd64-3.1.1.tar.bz2 && \
    tar -xvf teamspeak3-server_linux_amd64-3.1.1.tar.bz2 --transform s/teamspeak3-server_linux_amd64/teamspeak/&& \
    rm -v teamspeak3-server_linux_amd64-3.1.1.tar.bz2 && \
    chown -vR teamspeak:teamspeak teamspeak

WORKDIR /home/teamspeak
CMD ["sh", "ts3server_minimal_runscript.sh"]
