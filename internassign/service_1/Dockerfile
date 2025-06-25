###########################################
# Author: Jaya Krishna
# Date: 23-06-2025
# Description: Dockerfile for service 1
# Version: 1.0
# Usage: docker build -t <tag> .
###########################################

# Base image - This stage is used to build the Go application
FROM golang:1.22 AS builder

WORKDIR /app

# Copy the Go module files
COPY . .

RUN CGO_ENABLED=0 GOOS=linux go build -o service1 main.go

# Final stage - This stage is used to create a minimal image
FROM scratch

WORKDIR /app

# Copy the binary from the builder stage
COPY --from=builder /app/service1 .

# Expose the port the service will run on 
EXPOSE 8001

ENTRYPOINT ["./service1"]
