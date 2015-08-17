ccFROM node

# Install nodemon
RUN npm install -g nodemon

# Provides cached layer for node_modules
ADD package.json /tmp/package.json
RUN cd /tmp && npm install
RUN mkdir -p /vagrant/node && cp -a /tmp/node_modules /vagrant/node

# Define working directory
WORKDIR /vagrant/node

# Expose port
EXPOSE  8080

CMD ["nodemon", "index.js"]