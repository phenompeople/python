FROM amazonlinux

MAINTAINER paridhi "paridhimnnit@gmail.com"

# setting up python3.6
RUN yum update -y amazon-linux-extras && amazon-linux-extras install -y python3 && yum install -y libXext libSM libXrender wget unzip

# setting proper alias for python3 and pip3 and setting basic packages
RUN pip3 install --upgrade pip && pip3 install spacy && python3 -m spacy download en

# setting up chrome driver
RUN curl https://intoli.com/install-google-chrome.sh | bash
RUN wget https://chromedriver.storage.googleapis.com/2.37/chromedriver_linux64.zip 
RUN unzip chromedriver_linux64.zip && mv chromedriver /usr/bin/chromedriver && rm -f chromedriver_linux64.zip
