FROM debian

ENV EXTERNAL_URL="localhost"
ENV TERM="xterm-256color"
ENV DEBIAN_FRONTEND="noninteractive"

RUN apt-get update && \
    apt-get install -y apt-utils && \
    apt-get install -y curl openssh-server ca-certificates postfix postgresql postgresql-client ruby-full dialog libreadline7

WORKDIR /tmp
RUN curl -LO https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh
RUN bash script.deb.sh

EXPOSE 22
EXPOSE 80

RUN timeout 3m apt-get install -y gitlab-ce

RUN cat /opt/gitlab/embedded/bin/runsvdir-start&
