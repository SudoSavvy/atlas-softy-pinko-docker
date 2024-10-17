# Use the latest Ubuntu image
FROM ubuntu:latest

# Update and upgrade the system
RUN apt-get update && apt-get upgrade -y

# Install Python3 and pip3
RUN apt-get install -y python3 python3-pip

# Remove EXTERNALLY-MANAGED if necessary to avoid installation errors
RUN rm /usr/lib/python*/EXTERNALLY-MANAGED || true

# Install Flask using pip3
RUN pip3 install flask

# Set the working directory to /app
WORKDIR /app

# Copy the Python script to the container
COPY ./server.py /app/server.py

# Expose port 5252
EXPOSE 5252

# Run the Flask application
CMD ["python3", "server.py"]
