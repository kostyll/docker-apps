FROM debian:sid
MAINTAINER Markus Kosmal <code@m-ko-x.de>

COPY google-talkplugin_current_amd64.deb /src/google-talkplugin_current_amd64.deb

ADD  https://dl.google.com/linux/direct/google-chrome-beta_current_amd64.deb /src/google-chrome-beta_current_amd64.deb

RUN mkdir -p /usr/share/icons/hicolor && \
	apt-get update -yqq && apt-get install -yqq \
	ca-certificates \
	gconf-service \
	hicolor-icon-theme \
	libappindicator1 \
	libasound2 \
	libcanberra-gtk-module \
	libcurl3 \
	libexif-dev \
	libgconf-2-4 \
	libgl1-mesa-dri \
	libgl1-mesa-glx \
	libnspr4 \
	libnss3 \
	libpango1.0-0 \
	libv4l-0 \
	libxss1 \
	libxtst6 \
	wget \
	xdg-utils \
	--no-install-recommends && \
	dpkg -i '/src/google-chrome-beta_current_amd64.deb' && \
	dpkg -i '/src/google-talkplugin_current_amd64.deb' \
	&& rm -rf /var/lib/apt/lists/*

COPY local.conf /etc/fonts/local.conf

# Autorun chrome
ENTRYPOINT [ "/usr/bin/google-chrome" ]
CMD [ "--user-data-dir=/data", "--no-sandbox" ]
