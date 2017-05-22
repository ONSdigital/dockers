FROM ubuntu:16.04
ENV RUNTIME_PACKAGES="python3"
ENV BUILD_PACKAGES="curl build-essential python3-dev ca-certificates libssl-dev libffi-dev postgresql libpq-dev"

RUN apt-get update && apt-get install -y $RUNTIME_PACKAGES $BUILD_PACKAGES && curl -sS https://bootstrap.pypa.io/get-pip.py | python3


