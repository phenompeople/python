FROM amazonlinux:2
LABEL maintainer="admin.squad@phenompeople.com" 
ENV container docker
RUN yum install -q -e 0 -y wget make gcc-c++ libffi-devel openssl-devel sqlite-devel zlib-devel bzip2-devel shadow-utils yum-utils tar gzip&& \
	useradd -d /opt/deployment phenom -u 1004 && \
    mkdir -p /opt/deployment/scripts
ARG PYTHON_VERSION=3.7.0
ARG PYTHON_PIP_VERSION=20.2.3
ENV PYTHON_VERSION=${PYTHON_VERSION} \
    PYTHON_PIP_VERSION=${PYTHON_PIP_VERSION} \
    SETUP_DIRECTORY=/opt/python/cache
ADD setup /opt/deployment/scripts
RUN bash /opt/deployment/scripts/install.sh && \
    rm -rf /opt/deployment/scripts && \
    rm -rf /opt/python/cache/sources/Python-${PYTHON_VERSION}.tgz
RUN pip3 install --upgrade setuptools
ONBUILD RUN  yum update --security -q -y
ONBUILD RUN package-cleanup --oldkernels --count=1 -y -q
