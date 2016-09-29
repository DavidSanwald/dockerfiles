# Start with CUDA Theano base image
FROM ilikefoxes/cuda-theano-py3:latest
MAINTAINER David Sanwald <why.ever.not.berlin@gmail.com.com>

# Install dependencies
RUN apt-get update && apt-get install -y
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y libhdf5-dev

# Upgrade six, install h5py, keras
RUN pip3 install --upgrade six \
     h5py \
     pyaml \
     keras

# Set ~/keras as working directory
WORKDIR /root/keras
