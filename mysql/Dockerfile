# Use an official MySQL image as a base image
FROM mysql:5.7  

# Set the environment variables for MySQL
ENV MYSQL_ALLOW_EMPTY_PASSWORD=yes \
    MYSQL_DATABASE=cities \
    MYSQL_USER=shipping \
    MYSQL_PASSWORD=RoboShop@1

# Copy the SQL script to initialize the database schema
COPY shipping.sql /docker-entrypoint-initdb.d/

# Expose the MySQL port
EXPOSE 3306
