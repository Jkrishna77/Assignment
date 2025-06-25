###########################################
# Author: Jaya Krishna
# Date: 23-06-2025
# Description: Dockerfile for service 2 (Python Flask)
# Version: 1.0
# Usage: docker build -t <tag> .
###########################################

# Official Python image
FROM python:3.13-slim

RUN apt-get update && apt-get install -y curl && rm -rf /var/lib/apt/lists/*

WORKDIR /app

# Copy the files required for the image
COPY app.py .
COPY pyproject.toml .

# Install uv (fast Python package manager) and project dependencies
RUN pip install --no-cache-dir uv \
 && uv pip install --system --no-cache .

# Expose the port Flask app will run on
EXPOSE 8002

# Run the Flask app
ENTRYPOINT ["python", "app.py"]
