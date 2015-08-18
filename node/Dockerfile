FROM node

# Install nodemon
RUN npm install -g nodemon

# Provides cached layer for node_modules
RUN mkdir -p /vagrant/node
ADD package.json /vagrant/node/package.json
RUN cd /vagrant/node
RUN npm install

# Define working directory
WORKDIR /vagrant/node

# Expose port
EXPOSE  8080

CMD ["nodemon", "index.js"]