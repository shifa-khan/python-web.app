FROM ubuntu

# Set the working directory
WORKDIR /app

# Copy requirements.txt to the working directory
COPY requirements.txt .

# Update package lists and install required packages
RUN apt-get update && \
    apt-get install -y python3 python3-pip && \
    # Install Python packages from requirements.txt
    pip install -r requirements.txt

# Copy the ops directory to the working directory
COPY ops /app/ops

# Change the working directory to /app/ops
WORKDIR /app/ops

# Set the entrypoint command
ENTRYPOINT ["python3", "manage.py", "runserver", "0.0.0.0:8000"]