# alpine 3.3/NGINX with config and static files
FROM nginx:1.9.15-alpine
MAINTAINER Jyoti Bhanot <jyoti.bhanot30@gmail.com>

RUN apk update && \
    apk --update add unzip &&\
    apk add --update openssl nginx && \
    mkdir /etc/nginx/certificates && \
    openssl req \
    	-x509 \
    	-newkey rsa:2048 \
    	-keyout /etc/nginx/certificates/key.pem \
    	-out /etc/nginx/certificates/cert.pem \
    	-days 365 \
    	-nodes \
    	-subj /CN=localhost && \
    mkdir /www && \
    rm -rf /var/cache/apk/*
    
ADD https://s3.amazonaws.com/infra-assessment/static.zip /tmp/
RUN unzip -d /usr/share/nginx/html/ /tmp/static.zip \
    && rm -rf /tmp/static.zip

COPY default.conf /etc/nginx/conf.d/default.conf
