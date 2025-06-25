###########################################
# Author: Jaya Krishna
# Date: 23-06-2025
# Description: Dockerfile for Nginx reverse proxy
# Version: 1.0
# Usage: docker build -t <tag> .
###########################################

# Official Nginx image
FROM nginx:1.25-alpine

# Copy custom config file into the container
COPY default.conf /etc/nginx/conf.d/default.conf

# Expose port 80
EXPOSE 80