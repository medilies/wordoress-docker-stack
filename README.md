# REQUIRED IMAGES:

- PHP : web service
- MYSQL : db service
- PHPMyAdmin : phpmyadmin service

Get creative in selecting images that share the same base to economise RAM utilisation :) 

# ENV SETTINGS

Containers' timing TZ is set to +1GMT CET timezone by default in /docker-compose.yml

All services are set to use "root" as DB_USER

All services get DB_ROOT_PASSWORD from the *secret db_root_password*

Service name "db" is used as DB_HOSTNAME

DB_NAME is set in the *secret db_database* for the service db & web. If the DB doesn't already exist in the VOLUME wp-db a new one will be created on deploy

**IMPORTNT** mind renaming **wp-db VOLUME** if you want to launch other wordpress stacks!!

**NOTE** check port numbers you wanna use!

Services web and phpmyadmin are on separate networks

**/web/src/wp-config.php** contains defaults for WORDPRESS_DB_NAME, WORDPRESS_DB_USER, WORDPRESS_DB_PASSWORD, WORDPRESS_DB_HOST and WORDPRESS_DEBUG!

# ENV SETUP

Download **WordPress** and copy it to **/web/src**

