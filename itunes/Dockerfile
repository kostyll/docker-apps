FROM jess/wine
MAINTAINER Markus Kosmal <code@m-ko-x.de>

ADD https://jesss.s3.amazonaws.com/binaries/iTunesSetup.exe /usr/src/iTunesSetup.exe

RUN echo "wine /usr/src/iTunesSetup.exe" > /root/.bash_history

CMD [ "bash" ]
