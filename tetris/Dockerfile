FROM debian:jessie
MAINTAINER Markus Kosmal <code@m-ko-x.de>

RUN apt-get update -yqq && apt-get install -yqq \
	emacs \
	--no-install-recommends \
	&& rm -rf /var/lib/apt/lists/*

# start tetris
CMD ["/usr/bin/emacs", "-f", "tetris"]
