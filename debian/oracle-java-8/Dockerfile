FROM debian:latest

MAINTAINER Paulo Cardoso <paulohenrique@softbox.gmail.com>

# auto validate license
RUN apt-get update && \
    apt install -y curl software-properties-common gnupg && \
    echo "deb http://ppa.launchpad.net/webupd8team/java/ubuntu trusty main" | tee -a /etc/apt/sources.list && \
    echo "deb-src http://ppa.launchpad.net/webupd8team/java/ubuntu trusty main" | tee -a /etc/apt/sources.list && \
    echo oracle-java8-installer shared/accepted-oracle-license-v1-1 select true | /usr/bin/debconf-set-selections && \
    apt-key adv --keyserver keyserver.ubuntu.com --recv-keys EEA14886 && apt-get update && apt-get install -y curl dnsutils oracle-java8-installer ca-certificates && \
    wget https://github.com/Thrustjs/thrust/releases/download/0.3.0-1/thrust_0.3.0-1_all.deb && \
    dpkg -i thrust_0.3.0-1_all.deb && \
    mkdir -p /opt/code

ENV JAVA_HOME /usr/lib/jvm/java-8-oracle

COPY . /opt/code/

WORKDIR /opt/code/

RUN thrust install

EXPOSE 8778

CMD ["thrust","startup.js"]
