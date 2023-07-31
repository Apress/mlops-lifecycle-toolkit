FROM nvidia/cuda:12.0.1-base-ubuntu20.04

# Set bash as the default shell
ENV SHELL=/bin/bash

# Create a working directory
WORKDIR /lab/

# Build with some basic utilities
RUN apt-get update && apt-get install -y \
    python3-pip \
    apt-utils && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# create an alias for python 
RUN ln -s /usr/bin/python3 /usr/bin/python

RUN pip install \
    numpy \
    pandas \
    tensorflow \
    torch \
    jupyterlab==3.2.0

CMD ["jupyter", "lab", "--ip=0.0.0.0", "--port=8080", "--allow-root", "--no-browser"]

EXPOSE 8080
