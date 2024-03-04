FROM --platform=linux/amd64 python:3.11-slim as build

RUN apt-get update \
    && apt-get install -y --no-install-recommends --no-install-suggests \
    build-essential python3-dev default-libmysqlclient-dev pkg-config \
    && pip install --no-cache-dir --upgrade pip

WORKDIR /app
COPY ./requirements.txt /app
RUN pip install --no-cache-dir --requirement /app/requirements.txt
COPY . /app

EXPOSE 5000

CMD [ "python3","server.py" ]

