# Create a virtual environment with all tools installed
# ref: https://hub.docker.com/r/opensuse/tumbleweed
FROM opensuse/tumbleweed AS base

# Install system build dependencies
ENV PATH=/usr/local/bin:$PATH
RUN zypper update -y \
&& zypper install -y git patch gcc gcc-c++ cmake \
&& zypper clean -a
ENV CC=gcc CXX=g++

FROM base AS swig
RUN zypper update -y \
&& zypper install -y swig \
&& zypper clean -a
