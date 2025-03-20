# Use the Jenkins inbound agent as the base image
FROM jenkins/inbound-agent

# Switch to root user to perform installations
USER root

# Update package lists and install dependencies
RUN apt update && apt install -y curl

# Install Node.js (version 20.x) and npm
RUN curl -fsSL https://deb.nodesource.com/setup_20.x | bash - && \
    apt install -y nodejs

# Install Jest globally
RUN npm install -g jest

# Clean up
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

# Switch back to jenkins user
USER jenkins