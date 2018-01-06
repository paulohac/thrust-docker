FROM openjdk:8-alpine

LABEL maintainer="tarcisio@softbox.com.br"

RUN apk upgrade --update && \
    apk add --no-cache bash git openssh && \
    mkdir -p /opt && cd /opt && \
    git clone https://github.com/Thrustjs/thrust.git && \
    mkdir -p /app

WORKDIR /app

ENTRYPOINT ["java", "-jar", "/opt/thrust/dist/thrust.jar"]