# Use official Python base image
FROM python:3.8-slim

# Set working directory
WORKDIR /app

# Install system dependencies required for building Python packages
RUN apt-get update && apt-get install -y \
    gcc \
    build-essential \
    python3-dev \
    libffi-dev 
    
RUN pip install thriftpy2==0.4.16 py_zipkin==1.2.8

# Copy requirements file and install dependencies
COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt

# Copy application files
COPY . .

# Start the application
CMD ["python", "main.py"]
