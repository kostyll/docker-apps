FROM debian:sid
MAINTAINER Markus Kosmal <code@m-ko-x.de>

RUN sed -i.bak 's/sid main/sid main contrib/g' /etc/apt/sources.list && \
	apt-get update -yqq && apt-get install -yqq \
	bzip2 \
	ca-certificates \
	curl \
	flashplugin-nonfree \
	hicolor-icon-theme \
	libasound2 \
	libdbus-glib-1-2 \
	libgl1-mesa-dri \
	libgl1-mesa-glx \
	--no-install-recommends \
	&& rm -rf /var/lib/apt/lists/*

ENV FIREFOX_VERSION 38.0.5

RUN curl -sSL "https://ftp.mozilla.org/pub/mozilla.org/firefox/releases/latest/linux-x86_64/en-US/firefox-${FIREFOX_VERSION}.tar.bz2" -o /tmp/firefox.tar.bz2 \
	&& mkdir -p /opt/firefox \
	&& tar -xjf /tmp/firefox.tar.bz2 -C /opt/firefox --strip-components 1 \
	&& rm /tmp/firefox.tar.bz2* \
	&& ln -s /opt/firefox/firefox /usr/bin/firefox

COPY local.conf /etc/fonts/local.conf

ENTRYPOINT [ "/usr/bin/firefox" ]
