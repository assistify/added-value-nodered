FROM nodered/node-red-docker:latest

USER root
RUN apt-get --assume-yes install git
USER node-red

# Install node-packages which are needed for the flows
RUN npm install node-red-contrib-httpauth
RUN npm install node-red-dashboard

# Add some very basic settings
ADD ./settings.js /data/

# The config is needed to propagate the currently active project
ADD ./.config.json /data

ARG ACCESS_TOKEN
RUN git clone https://${ACCESS_TOKEN}@github.com/assistify/assistify-workflows.git /data/projects/assistify-workflows/
