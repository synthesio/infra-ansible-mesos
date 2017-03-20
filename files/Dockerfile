FROM debian:jessie
MAINTAINER Fred de Villamil <fdevillamil@synthesio.com>

RUN apt-get update
RUN apt-get install -y \
  autoconf \
  automake \
  build-essential \ 
  git \
  libcurl3 \
  libtool \
  libapr1-dev \ 
  libsvn-dev \
  libcurl4-nss-dev \
  libsasl2-dev \ 
  libsasl2-modules \ 
  libssl-dev \
  make \
  maven \ 
  openjdk-7-jdk \
  python-dev \ 
  ruby \ 
  ruby-dev \
  tar \
  wget \
  zlib1g-dev

RUN gem install fpm
RUN git clone https://github.com/mesosphere/mesos-deb-packaging.git
RUN cd mesos-deb-packaging-master && ./build_mesos --ref 1.2.0
RUN mkdir -p /mnt/artifacts
CMD mv mesos-deb-packaging-master/pkg.deb /mnt/artifacts/mesos-1.2.0.deb
