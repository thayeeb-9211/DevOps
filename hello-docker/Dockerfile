# Steps for creating Docker image
# Use the official Python image from Docker Hub
FROM python:latest

# Set the working directory inside the container
WORKDIR /app

# Copy your Python script into the container
COPY app.py .

# Print a message for debugging purposes
RUN echo "Building the Python application..."

# Command to run the Python script when the container starts
CMD ["python", "app.py"]

