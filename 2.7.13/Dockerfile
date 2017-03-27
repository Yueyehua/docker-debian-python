FROM yueyehua/debian-base
MAINTAINER Richard Delaplace "rdelaplace@yueyehua.net"
LABEL version="1.0.0"

ENV _PYTHON_VERSION=2.7.13

# Apt update and upgrade
RUN \
  apt-get -qq update && \
  apt-get -qq dist-upgrade -y;

# Install dependencies
RUN \
  apt-get -qq -y install gcc git-core build-essential libffi-dev libssl-dev \
    libcurl4-openssl-dev libreadline-dev bzip2 sqlite3;

# Clean all
RUN \
  apt-get -qq clean autoclean;

# Install pyenv
RUN \
  git clone https://github.com/pyenv/pyenv.git ~/.pyenv;

# Install Python
RUN \
  /root/.pyenv/bin/pyenv install ${_PYTHON_VERSION} && \
  /root/.pyenv/bin/pyenv global ${_PYTHON_VERSION};

# Export PATH
ENV PATH=$PATH:/root/.pyenv/bin:/root/.pyenv/shims

VOLUME ["/sys/fs/cgroup"]
CMD  ["/lib/systemd/systemd"]
