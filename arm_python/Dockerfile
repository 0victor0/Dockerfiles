#This is a demo web app powered by python on RPi

FROM armhf/python

WORKDIR /webapp

ENV PYPORT=5555

RUN apt-get update

#Files added to this directory will be exposed by web app
COPY webapp/ /webapp

EXPOSE $PYPORT

ENTRYPOINT python -m http.server $PYPORT
