# Use the official Python image
FROM python:3.9-slim

# Set the working directory
WORKDIR /app

#Install required packages for system
RUN apt-get update \
    && apt-get upgrade -y \
    && apt-get install -y gcc default-libmysqlclient-dev pkg-config \
    && rm -rf /var/lib/apt/lists

# Copy the requirements.txt into the container
COPY requirements.txt /app

# Install the dependencies
RUN pip install mysqlclient
RUN pip install --no-cache-dir -r requirements.txt

#Copy rest of code - Doing here because we dont pip install to happen everytime when we change code.

COPY . .

# Expose port 5500 for the Flask app
EXPOSE 5500

# Set environment variables
ENV FLASK_APP=app.py
ENV MYSQL_HOST=database
ENV MYSQL_ROOT_PASSWORD=rootpassword
ENV MYSQL_DATABASE=tecvinson_registration

# Run the application
ENTRYPOINT [ "python" ]
CMD ["app.py"]
#CMD ["flask", "run", "--host=0.0.0.0","--port=5500"]

#https://ibrahims.medium.com/flask-app-with-mysql-docker-setup-fa38d979e2cf