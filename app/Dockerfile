# pull official base image
FROM python:3.9.6-alpine

# set work directory
WORKDIR /usr/src/app

# set environment variables
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# install psycopg2 dependencies
RUN apk update \
    && apk --no-cache add \
		postgresql-dev \
		gcc \
		python3-dev \
		musl-dev \
		python3-dev \
		build-base \
		openssl \
		bash \
		git \
		meson \
		py3-pip \
		sudo \
		# Pillow dependencies
		freetype-dev \
		fribidi-dev \
		harfbuzz-dev \
		jpeg-dev \
		lcms2-dev \
		openjpeg-dev \
		tcl-dev \
		tk-dev \
		zlib-dev

# install dependencies
RUN pip install --upgrade pip
COPY ./requirements.txt .
RUN pip install -r requirements.txt

# copy project
COPY . .

