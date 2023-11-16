# Use an official MySQL image as a base image
FROM mysql:latest

# Set the environment variables for MySQL
ENV MYSQL_ROOT_PASSWORD=root_password
ENV MYSQL_DATABASE=my_database
ENV MYSQL_USER=my_user
ENV MYSQL_PASSWORD=my_password

# Copy the SQL script to initialize the database schema
COPY shipping.sql /docker-entrypoint-initdb.d/

# Expose the MySQL port
EXPOSE 3306
