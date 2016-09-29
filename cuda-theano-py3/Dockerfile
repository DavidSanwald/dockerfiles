# Start with cuDNN base image
FROM nvidia/cuda:8.0-cudnn5-devel
MAINTAINER David Sanwald <why.ever.not.berlin@gmail.com>

# Install git, wget, python3-dev , pip 3 and other dependencies
RUN apt-get update && apt-get install -y \
  git \
  libopenblas-dev \
  wget \
  python3-dev \
  python3-pip \
  python3-nose \
  python3-numpy \
  cython3 \

RUN DEBIAN_FRONTEND=noninteractive apt-get install -y python3-scipy


# Set CUDA_ROOT
ENV CUDA_ROOT /usr/local/cuda/bin
# Install bleeding-edge Theano
RUN pip3 install --upgrade --no-deps git+git://github.com/Theano/Theano.git
# Set up .theanorc for CUDA
RUN echo "[global]\ndevice=gpu\nfloatX=float32\noptimizer_including=cudnn\n[lib]\ncnmem=0.1\n[nvcc]\nfastmath=True" > /root/.theanorc
