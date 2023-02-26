FROM ubuntu

# Python base tools
RUN apt-get update && apt-get install -y --no-install-recommends \
        python3             \
        python3-pip         \
        python3-setuptools  \
        python3-venv        \
    && rm -rf /var/lib/apt/lists/*

RUN ln /usr/bin/python3 /usr/bin/python

ENV PYTHONIOENCODING=utf-8

#COPY pylint /usr/bin

WORKDIR /build

# Install using pip
COPY ./requirements.txt .
RUN python3 -m pip install -r requirements.txt

# Act as local user, not root, with workdir homedir
RUN groupadd -r dbw && useradd --no-log-init -r -g dbw dbw
WORKDIR /home/dbw
USER dbw
