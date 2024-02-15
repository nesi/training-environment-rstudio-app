FROM rocker/rstudio:latest

RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y \
        curl \
        dnsutils \
        git \
        jq \
        ldap-utils \
        libnss-ldapd \
        libpam-ldapd \
        less \
        nano \
        nodejs \
        nscd \
        nslcd \
        rsync \
        unzip \
        vim \
        wget \
        zip \
    && rm -rf /var/lib/apt/lists/*

ARG KUBECTL_VERSION=v1.28.5
RUN curl -LO https://dl.k8s.io/release/$KUBECTL_VERSION/bin/linux/amd64/kubectl \
    && mv kubectl /usr/bin/kubectl \
    && chmod +x /usr/bin/kubectl

ARG UTILS_HASH=b2430738bd8d980febbc8b3920c413e001ae4128
RUN git clone https://github.com/chrisdjscott/ood-k8s-utils.git /opt/ood-k8s-utils \
    && cd /opt/ood-k8s-utils \
    && git checkout $UTILS_HASH \
    && chmod +x /opt/ood-k8s-utils/files/* \
    && mv /opt/ood-k8s-utils/files/* /bin/ \
    && rm -rf /opt/ood-k8s-utils

RUN echo "#!/bin/bash" > /bin/module \
    && chmod +x /bin/module
