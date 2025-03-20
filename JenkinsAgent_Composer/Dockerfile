# Use the Jenkins inbound agent as the base image
FROM jenkins/inbound-agent

# Switch to root user to perform installations
USER root

# Update package lists and install PHP
RUN apt update && apt install -y php

# Install PHP extensions and utilities
RUN apt install -y php-curl php-xml zip unzip

# Install PHP mbstring extension
RUN apt install -y php-mbstring

# Download Composer installer
RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" \
    # Verify the installer's integrity
    php -r "if (hash_file('sha384', 'composer-setup.php') === 'dac665fdc30fdd8ec78b38b9800061b4150413ff2e3b6f88543c636f7cd84f6db9189d43a81e5503cda447da73c7e5b6') { echo 'Installer verified'.PHP_EOL; } else { echo 'Installer corrupt'.PHP_EOL; unlink('composer-setup.php'); exit(1); }"

# Run Composer installer
RUN php composer-setup.php

# Remove Composer installer
RUN php -r "unlink('composer-setup.php');"

# Move Composer to a directory in the system PATH
RUN mv composer.phar /usr/local/bin/composer
