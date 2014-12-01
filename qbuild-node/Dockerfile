FROM ubuntu-debootstrap:14.04
MAINTAINER lksv "lukas.svoboda@gmail.com"

RUN export DEBIAN_FRONTEND=noninteractive
ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update -qq && apt-get upgrade -y

#RUN apt-get install -y --force-yes wget apt-utils
#RUN wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | apt-key add -
#RUN echo "deb http://dl.google.com/linux/chrome/deb/ stable main" >> /etc/apt/sources.list.d/google-chrome.list

RUN apt-get update -qq && apt-get upgrade -y

RUN apt-get install -y --force-yes \
  apt-utils \
  build-essential \
  coreutils \
  curl \
  daemontools \
  git \
  language-pack-en \
  libbz2-dev \
  libcurl4-openssl-dev \
  libevent-dev \
  libglib2.0-dev \
  libjpeg-dev \
  libncurses5-dev \
  libpq-dev \
  libpq5 \
  libreadline6-dev \
  libssl-dev \
  libxml2-dev \
  libxslt-dev \
  python \
  python-dev \
  ruby \
  ruby-dev \
  socat \
  syslinux \
  tar \
  telnet \
  zip \
  nodejs \
  nodejs-legacy \
  npm \
  vim \
  sudo \
  xvfb \
  wget \
  firefox

# Install Chrome

RUN apt-get install -y ca-certificates
# RUN wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb -P /tmp/
# RUN dpkg -i /tmp/google-chrome-stable_current_amd64.deb || true
# RUN apt-get install -fy

RUN apt-get install -y chromium-browser

# Java
RUN apt-get -y  install openjdk-7-jre-headless unzip

# Recording (usage: /usr/bin/Xvfb $DISPLAY -ac -screen 0 1024x768x16 2>/dev/null 2>/dev/null &)

RUN apt-get install libav-tools -y

RUN npm install -g bower grunt grunt-cli
RUN rm -rf /var/cache/apt/archives/*.deb /root/* /tmp/* /var/lib/apt/lists/*

ADD ./builder/ /build
