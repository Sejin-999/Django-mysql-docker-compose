# pull official base image
FROM python:3.12.0a3-alpine

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

ARG DJANGO_ALLOWED_HOSTS
ARG DJANGO_SECRET_KEY
ARG DJANGO_CORS_ORIGIN_WHITELIST

ENV DJANGO_ALLOWED_HOSTS $DJANGO_ALLOWED_HOSTS
ENV DJANGO_SECRET_KEY $DJANGO_SECRET_KEY
ENV DJANGO_CORS_ORIGIN_WHITELIST $DJANGO_CORS_ORIGIN_WHITELIST

WORKDIR /backend
COPY requirements.txt /backend/

#RUN apt-get update && apt-get install -y curl  #우분투 환경이면 넣어야할듯???

RUN pip install --upgrade pip
RUN pip install -r requirements.txt
RUN pip install pymysql
COPY . /backend/