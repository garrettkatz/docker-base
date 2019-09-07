# Use an official Python runtime as a parent image
FROM python:3

MAINTAINER Garrett Katz <garrett.katz@gmail.com>

# Copies any source-code you've written into the image
COPY src/ /src

# Copies all of the pip .whl files into the image to install them
COPY docker/vendor/ /vendor

# Installs all of the .whl files
RUN set -ex \
  && pip install /vendor/numpy-1.17.2-cp37-cp37m-manylinux1_x86_64.whl \
  && pip install /vendor/scipy-1.3.1-cp37-cp37m-manylinux1_x86_64.whl \
  && pip install /vendor/six-1.12.0-py2.py3-none-any.whl \
  && pip install /vendor/Pillow-6.1.0-cp37-cp37m-manylinux1_x86_64.whl \
  && pip install /vendor/torch-1.2.0+cpu-cp37-cp37m-manylinux1_x86_64.whl \
  && pip install /vendor/torchvision-0.4.0+cpu-cp37-cp37m-manylinux1_x86_64.whl

# Cleans up by deleting the .whl files from the image
RUN set -ex \
  && rm -rf /vendor

# Starts in a bash shell when you run the image in a container
CMD ["/bin/bash"]

