# cf-maven
cloud foundry image ( generic) 

	FROM alpine:latest 
	
	MAINTAINER Joby Pooppillikudiyil
	
	RUN apk update 
	
	RUN apk add openjdk8
	RUN apk add jq
	RUN apk add curl
	RUN apk add bash
	RUN apk add maven 
	RUN apk add --update nodejs npm
	RUN apk add --update npm

	ADD https://cli.run.pivotal.io/stable?release=linux64-binary&version=6.49.0 /tmp/cf-cli.tgz
	RUN mkdir -p /usr/local/bin && tar -xzf /tmp/cf-cli.tgz -C /usr/local/bin && cf --version && rm -f /tmp/cf-cli.tgz

