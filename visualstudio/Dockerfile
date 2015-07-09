FROM jess/chromium
MAINTAINER Markus Kosmal <code@m-ko-x.de>

RUN apt-get update -yqq && apt-get install -yqq \
	build-essential \
	ca-certificates \
	curl \
	git \
	libasound2 \
	libgconf-2-4 \
	libgnome-keyring-dev \
	libgtk2.0-0 \
	libnss3 \
	libpci3 \
	libxtst6 \
	unzip \
	--no-install-recommends

ENV HOME /home/user
RUN useradd --create-home --home-dir $HOME user \
	&& chown -R user:user $HOME

# install node
RUN curl -sL https://deb.nodesource.com/setup | bash - \
    && apt-get update && apt-get install -y \
	nodejs \
	&& rm -rf /var/lib/apt/lists/* \
	&& npm update -g

# download the source
RUN curl -sSL https://jesss.s3.amazonaws.com/binaries/VSCode-linux-x64.zip -o /tmp/vs.zip \
	&& unzip /tmp/vs.zip -d /usr/src/ \
	&& rm -rf /tmp/vs.zip \
	&& ln -snf /usr/src/VSCode-linux-x64/Code /usr/local/bin/code

COPY start.sh /usr/local/bin/start.sh
WORKDIR $HOME

ENTRYPOINT [ "/usr/local/bin/start.sh" ]
