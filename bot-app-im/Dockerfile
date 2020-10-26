FROM phenompeople/python:3.6.3
MAINTAINER Admin Squad "admin.squad@phenompeople.com"
ARG APP_HOME=/opt/deployment
ARG PROJECT_NAME="chatbot-app-im"
ENV PYTHONUNBUFFERED=1
ENV APP_HOME=${APP_HOME} \
    PROJECT_NAME=${PROJECT_NAME} \
    PROJECT_HOME=${APP_HOME}/${PROJECT_NAME}
COPY pyproject.toml ${PROJECT_HOME}/
WORKDIR ${PROJECT_HOME}
ENV PYTHONPATH=${PROJECT_HOME}
RUN pip3 install poetry==1.0.9
RUN poetry config virtualenvs.create false
RUN yum -y install git-core
COPY poetry.lock ${PROJECT_HOME}/
RUN pip3 install --upgrade pip
RUN pip3 install -U --ignore-installed setuptools
RUN poetry install --extras transformers
