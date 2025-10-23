FROM mcr.microsoft.com/devcontainers/typescript-node:22-bookworm

# Use noninteractive frontend for apt
ENV DEBIAN_FRONTEND=noninteractive

# Install minimal tools and build deps for native modules
RUN apt-get update \
  && apt-get install -y\
    ca-certificates \
    build-essential \
    bash-completion \
    iputils-ping \
    net-tools \
    vim \
    git \
    curl \
    wget \
    less \
    groff \
    default-jre \
    graphviz \
    fonts-ipafont \
  && apt-get clean -y \
  && rm -rf /var/lib/apt/lists/*

# Configure locale
RUN echo 'ja_JP.UTF-8 UTF-8' >> /etc/locale.gen && \
    locale-gen && \
    update-locale LANG=ja_JP.UTF-8
RUN ln -sf /usr/share/zoneinfo/Asia/Tokyo /etc/localtime
