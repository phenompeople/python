FROM amazonlinux

MAINTAINER paridhi "paridhimnnit@gmail.com"

# setting up python3.6
RUN yum update -y amazon-linux-extras && amazon-linux-extras install -y python3

# setting proper alias for python3 and pip3 and setting basic packages
RUN pip3 install --upgrade pip && pip3 install spacy && python3 -m spacy download en
