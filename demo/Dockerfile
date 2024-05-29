# Use the Red Hat Universal Base Image (UBI) as the base image
FROM registry.access.redhat.com/ubi8/ubi

# Set the working directory
WORKDIR /app

# Copy requirements.txt to the working directory
COPY requirements.txt .

# Install Python 3 and pip
RUN yum install -y python3 python3-pip

# Install Python packages from requirements.txt
RUN pip3 install -r requirements.txt

# Copy the ops directory to the working directory
COPY ops /app/ops

# Copy manage.py to the working directory
COPY manage.py /app/

# Change the working directory to /app/ops
WORKDIR /app/ops

# Expose the port on which the Django server will run (assuming it's port 8000)
EXPOSE 8000

# Set the entrypoint command
ENTRYPOINT ["python3", "manage.py", "runserver", "0.0.0.0:8000"]
