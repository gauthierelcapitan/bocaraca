FROM continuumio/anaconda3

# Install deps
RUN apt-get update && apt-get install -y \
  curl \
  gcc \
  g++ \
  libgeos-dev \
  bash \
  ffmpeg \
  libsm6 \
  libxext6 \
  pkg-config \
  libgtk2.0-dev

# Install Python3
RUN mkdir /opt/notebooks
RUN mkdir /opt/pip
COPY ./docker/local/python/requirements.txt /opt/pip/requirements.txt
RUN pip3 install --upgrade pip
RUN pip3 install -r /opt/pip/requirements.txt

# Install Zsh
RUN sh -c "$(wget -O- https://github.com/deluan/zsh-in-docker/releases/download/v1.1.2/zsh-in-docker.sh)"
