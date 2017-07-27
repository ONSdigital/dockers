FROM ubuntu:15.04

ENV RUNTIME_PACKAGES="python3"
ENV BUILD_PACKAGES="curl build-essential python3-dev ca-certificates libssl-dev libffi-dev"
ENV USED_PACKAGES="git gcc make build-essential python3-dev python3-reportlab"

ADD requirements.txt /crypto/requirements.txt

# Install all dependencies, cleanup and reinstall python + other useful packages.
# apt's cleanup also uninstalls python, so we have to install again..

RUN apt-get update && apt-get install -y $RUNTIME_PACKAGES $BUILD_PACKAGES \
	&& curl -sS https://bootstrap.pypa.io/get-pip.py | python3 \
	&& pip3 install --no-cache-dir -U -I -r /crypto/requirements.txt \
	&& apt-get remove --purge -y $BUILD_PACKAGES $(apt-mark showauto) \
	&& apt-get install -y $RUNTIME_PACKAGES $USED_PACKAGES \
	&& rm -rf /var/lib/apt/lists/*
