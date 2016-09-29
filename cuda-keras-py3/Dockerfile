# Start with CUDA Theano base image
FROM ilikefoxes/cuda-theano-py3:latest
MAINTAINER David Sanwald <why.ever.not.berlin@gmail.com.com>

# Install dependencies
RUN apt-get update && apt-get install -y \
  libhdf5-dev \
  python-h5py \
  python-yaml

# Upgrade six
RUN pip3 install --upgrade six

# Clone Keras repo and move into it
RUN cd /root && git clone https://github.com/fchollet/keras.git && cd keras && \
  # Install
  python setup.py install

# Set ~/keras as working directory
WORKDIR /root/keras
