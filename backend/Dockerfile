# FROM node:20
# EXPOSE 8080
# ENV DB_HOST=mysql
# RUN useradd expense
# RUN mkdir /opt/server
# RUN chown expense:expense -R /opt/server
# WORKDIR /opt/server
# COPY package.json .
# COPY *.js .
# RUN npm install
# CMD [ "node","index.js" ]


# Base image
FROM node:20


# Install MySQL client
RUN apt-get update && \
    apt-get install -y default-mysql-client && \
    rm -rf /var/lib/apt/lists/*

# Set environment variables
ENV DB_HOST=mysql

# Add a new user
RUN useradd -m expense

# Create and set permissions for the server directory
RUN mkdir -p /opt/server && chown expense:expense -R /opt/server

# Set working directory
WORKDIR /opt/server

# Copy package.json and install dependencies
COPY package.json .
RUN npm install

# Copy application code
COPY *.js .

# Expose the server port
EXPOSE 8080

# Run the application as the expense user
USER expense
CMD ["node", "index.js"]
