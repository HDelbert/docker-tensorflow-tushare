# Copyright (c) Meng Hu
# Distributed under the terms of the Modified BSD License.
FROM jupyter/scipy-notebook

MAINTAINER Meng Hu <humeng1220@126.com>

USER $NB_USER

# Install numpy
RUN conda install --quiet --yes -c conda-forge opencv
RUN conda install --quiet --yes -c anaconda numpy

