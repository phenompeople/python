FROM phenompeople/python:3.6.3
LABEL maintainer="gaurav.vergiya@phenompeople.com"
ENV container docker
ADD requirements.txt /
RUN pip3 install  -r requirements.txt
RUN python3 -m spacy download en_core_web_lg
RUN python3 -m spacy download fr_core_news_md
RUN python3 -m spacy download es_core_news_md
