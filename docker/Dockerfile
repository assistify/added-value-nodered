FROM nodered/node-red-docker:latest


# Install node-packages which are needed for the flows
RUN npm install node-red-contrib-httpauth
RUN npm install node-red-dashboard

# Add some very basic settings
ADD ./settings.js /data/

# Copy the downloaded flow-files
COPY --chown=node-red:node-red ./projects /data/projects
