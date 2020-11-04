
FROM python:3.8-alpine

COPY ./docker/python/requirements.txt /tmp/requirements.txt

WORKDIR /application

RUN pip install -U setuptools
RUN easy_install distribute

RUN apk update \
    && apk add gcc \
        make \
        git

RUN pip install --no-cache-dir -r /tmp/requirements.txt

CMD exec /bin/bash -c "trap : TERM INT; sleep infinity & wait"
