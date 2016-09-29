FROM ilikefoxes/cuda-miniconda-theano
MAINTAINER David Sanwald <why.ever.not.berlin@gmail.com>

RUN apt-get update && apt-get install -y \
  git \
  wget \
  libopenblas-dev \

RUN conda install -y \
    numpy \
    scipy \
    pyaml \
    h5py

ENV CUDA_ROOT /usr/local/cuda/bin
# Install bleeding-edge Theano
RUN pip install --upgrade --no-deps git+git://github.com/Theano/Theano.git
# Set up .theanorc for CUDA
RUN echo "[global]\ndevice=gpu\nfloatX=float32\noptimizer_including=cudnn\n[lib]\ncnmem=0.1\n[nvcc]\nfastmath=True" > /root/.theanorc