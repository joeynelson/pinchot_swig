# Create a virtual environment with all tools installed
# ref: https://hub.docker.com/_/debian
FROM debian:latest AS base

# Install system build dependencies
ENV PATH=/usr/local/bin:$PATH
RUN apt-get update -qq \
&& apt-get install -yq \
 git wget libssl-dev build-essential \
&& apt-get clean \
&& rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# Install CMake 3.18.1
RUN wget "https://cmake.org/files/v3.18/cmake-3.18.1-Linux-x86_64.sh" \
&& chmod a+x cmake-3.18.1-Linux-x86_64.sh \
&& ./cmake-3.18.1-Linux-x86_64.sh --prefix=/usr/local/ --skip-license \
&& rm cmake-3.18.1-Linux-x86_64.sh

FROM base AS swig
RUN apt-get update -qq \
&& apt-get install -yq swig \
&& apt-get clean \
&& rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
