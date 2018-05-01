# php apache docker image
FROM php:7-apache

# Enable Apache ldap auth module
RUN a2enmod authnz_ldap

# Add ldap rules to apache's conf-enabled dir
COPY Docker/ldap-demo.conf /etc/apache2/conf-enabled/

# Add debugging help if you need it
# RUN echo "LogLevel debug" >> /etc/apache2/apache2.conf

# Convenient working directory
WORKDIR /var/www/html/demo

# Configure apache
COPY Docker/.htaccess ./.htaccess

# Copy the project files we need
COPY index.php ./
