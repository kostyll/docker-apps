FROM debian:jessie
MAINTAINER Markus Kosmal <code@m-ko-x.de>

RUN apt-get update -yqq && apt-get install -yqq \
	ca-certificates \
	curl \
	software-properties-common \
	--no-install-recommends && \
	curl -sSL https://www.virtualbox.org/download/oracle_vbox.asc | apt-key add - && \
	echo "deb http://download.virtualbox.org/virtualbox/debian jessie contrib" >> /etc/apt/sources.list.d/virtualbox.list && \
	apt-get update && \
	apt-get install -y \
	virtualbox \
	&& rm -rf /var/lib/apt/lists/*

ENTRYPOINT	[ "/usr/bin/virtualbox" ]
