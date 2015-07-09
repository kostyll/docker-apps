FROM debian:jessie
MAINTAINER Markus Kosmal <code@m-ko-x.de>

ENV DEBIAN_FRONTEND noninteractive

# multi-arch
RUN dpkg --add-architecture i386 && \
	apt-get update && apt-get install -y \
	curl \
	--no-install-recommends


# install
RUN curl http://download.skype.com/linux/skype-debian_4.3.0.37-1_i386.deb > /usr/src/skype.deb && \ 
	dpkg --force-depends -i /usr/src/skype.deb && \
	apt-get install -fyqq \
	&& rm -rf /var/lib/apt/lists/*

# start
ENTRYPOINT ["skype"]
