FROM ubuntu:14.04

MAINTAINER Meng.Hu <humeng.jade@gmail.com>

ENV DEBIAN_FRONTEND=noninteractive \
    NOTEBOOKS_DIR="/notebooks"

RUN apt-get update \
  && apt-get install -y --no-install-recommends \
    build-essential \
    curl \
    libfreetype6-dev \
    libpng12-dev \
    libzmq3-dev \
    libxml2 \
    pkg-config \
    python \
    python-dev \
    python-lxml \
    python-psycopg2 \
    rsync \
    software-properties-common \
    unzip \
    libblas-dev \
    liblapack-dev \
    libmysqld-dev \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/*

RUN curl -O https://bootstrap.pypa.io/get-pip.py \
  && python get-pip.py \
  && rm get-pip.py

# Install dependences
RUN pip --no-cache-dir install \
    ipykernel \
    jupyter \
    matplotlib \
    numpy \
    scipy \
    pandas \
    lxml \
    cvxopt \
  && python -m ipykernel.kernelspec

# Install tushare
RUN pip --no-cache-dir install \
    sqlalchemy \
    pymongo \
    MySQL-python \
    tushare

COPY jupyter_notebook_config.py /root/.jupyter/

COPY run_jupyter.sh /

# IPython
EXPOSE 8888

VOLUME ["${NOTEBOOKS_DIR}"]

WORKDIR "${NOTEBOOKS_DIR}"

CMD ["/run_jupyter.sh"]
