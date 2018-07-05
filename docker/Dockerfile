FROM nodered/node-red-docker:latest

USER root

RUN apt-get update && \
  apt-get install -y git

ARG ACCESS_TOKEN
RUN echo $ACCESS_TOKEN

RUN git clone https://${ACCESS_TOKEN}@github.com/assistify/assistify-wf-ci-deploy.git
RUN mv assistify-wf-ci-deploy/* /data/

USER node-red