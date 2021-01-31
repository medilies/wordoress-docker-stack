# REQUIRED IMAGES:

- PHP : web service
- MYSQL : db service
- PHPMyAdmin : phpmyadmin service

Get creative in selecting images that share the same base to economise RAM utilisation :) 

# ENV SETTINGS

Containers' timing TZ is set to +1GMT CET timezone by default in /docker-compose.yml

All services are set to use "root" as DB_USER

The *secret db_root_password* is used by all services to set:
- db: MYSQL_ROOT_PASSWORD_FILE
- web: WORDPRESS_DB_PASSWORD_FILE
- phpmyadmin: PMA_PASSWORD_FILE

The *secret db_database* is used by db & web to set:
- db: MYSQL_DATABASE_FILE and create the DB if it doesn't already exist in the **VOLUME wp-db**
- web: WORDPRESS_DB_NAME_FILE

Service name "db" is used as DB_HOSTNAME

**IMPORTNT** mind renaming **wp-db VOLUME** if you want to launch other wordpress stacks!!

**NOTE** check port numbers you wanna use!

Services web and phpmyadmin are on separate networks

**/web/src/wp-config.php** contains defaults for: 
- WORDPRESS_DB_NAME
- WORDPRESS_DB_USER
- WORDPRESS_DB_PASSWORD
- WORDPRESS_DB_HOST
- WORDPRESS_DEBUG

# ENV SETUP

Download **WordPress** and copy it to **/web/src**

