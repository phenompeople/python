#Base image
FROM amazonlinux:2
LABEL maintainer="rajesh.jonnalagadda@phenompeople.com" 
ENV container docker
RUN yum install -q -e 0 -y wget make gcc-c++ openssl-devel sqlite-devel zlib-devel bzip2-devel shadow-utils yum-utils tar gzip&& \
	useradd -d /opt/deployment phenom -u 1004 && \
    mkdir -p /opt/deployment/scripts
ARG PYTHON_VERSION=2.7.13
ARG PYTHON_PIP_VERSION=9.0.1
ENV PYTHON_VERSION=${PYTHON_VERSION} \
    PYTHON_PIP_VERSION=${PYTHON_PIP_VERSION} \
    CFLAGS="$CFLAGS -fPIC" \
    PYTHONPATH=/usr/local/lib/python2.7/site-packages \
    SETUP_DIRECTORY=/opt/python/cache
ADD setup /opt/deployment/scripts
RUN /opt/deployment/scripts/install.sh && \
    yum clean all && \
    rm -rf /opt/deployment/scripts && \
    rm -rf /opt/python/cache/sources/Python-${PYTHON_VERSION}.tgz
ONBUILD RUN  yum update --security -q -y
ONBUILD RUN package-cleanup --oldkernels --count=1 -y -q