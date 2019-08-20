FROM amazonlinux

MAINTAINER paridhi "paridhimnnit@gmail.com"

# setting python 3.6
RUN yum update -y amazon-linux-extras && amazon-linux-extras install -y python3 \
	&& yum install -y wget unzip

# downloading embedding file and saving to appropriate path
RUN wget https://dl.fbaipublicfiles.com/fasttext/vectors-english/wiki-news-300d-1M.vec.zip \
	&& mkdir -p /opt/ext_data \
    && unzip wiki-news-300d-1M.vec.zip -d /opt/ext_data \
    && rm -f wiki-news-300d-1M.vec.zip
	
# setting proper alias for python3 and pip3 and setting basic packages
RUN pip3 install --upgrade pip && pip3 install spacy \
	&& python3 -m spacy download en
