# Use the MySQL 8.0 image
FROM mysql:8.0

# Set environment variables for MySQL
ENV MYSQL_ROOT_PASSWORD=ExpenseApp@1 \
    MYSQL_USER=expense \
    MYSQL_PASSWORD=ExpenseApp@1 \
    MYSQL_DATABASE=transactions

# Copy SQL initialization scripts to the MySQL entrypoint directory
COPY scripts/*.sql /docker-entrypoint-initdb.d/ 
