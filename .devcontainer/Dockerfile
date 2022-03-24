FROM python:3.6-alpine
ENV PYTHONUNBUFFERED 1
# Creating working directory
RUN mkdir /code
WORKDIR /code
# Copying requirements
COPY ./ .
RUN apk add --no-cache --virtual .build-deps \
    ca-certificates gcc postgresql-dev linux-headers musl-dev \
    libffi-dev jpeg-dev zlib-dev \
    && pip install -r requirements.txt

RUN apk update
RUN apk add git