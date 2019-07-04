# Use an official centos7 image
FROM centos:7

MAINTAINER paridhi "paridhi.shukla@phenompeople.com"

RUN yum update -y \
	&& yum install -y https://centos7.iuscommunity.org/ius-release.rpm \
    && yum install -y python36u python36u-libs python36u-devel python36u-pip \
    && yum groupinstall -y 'development tools' \
	&& yum install -y wget gcc libffi-devel python-devel openssl-devel libev-devel

# setting proper alias for python3 and pip3 and setting basic packages
RUN ln -s /usr/bin/pip3.6 /bin/pip3 && ln -s /usr/bin/python3.6 /usr/bin/python3 \
	&& pip3 install --upgrade pip && pip3 install spacy && pip3 install -U setuptools \
	&& python3 -m spacy download en
