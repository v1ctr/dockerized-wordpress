# Installing WordPress With Docker Compose
This is a Starter Template based on 
[How To Install WordPress With Docker Compose | Digital Ocean](https://www.digitalocean.com/community/tutorials/how-to-install-wordpress-with-docker-compose)

## Todo:
1. Replace ```example.com``` in ```nginx-conf/nginx.conf```with your own domain.
2. Create ```.env``` file in main project directory ```dockerized-wordpress``` and define 
   environment variables:
   ```
   MYSQL_ROOT_PASSWORD=your_root_password
   MYSQL_USER=your_wordpress_database_user
   MYSQL_PASSWORD=your_wordpress_database_password
   ```
3. Replace ```dummy@example.com``` in ```dockerized-wordpress/docker-compose.yml``` with
   your preferred email for registration and recovery.
4. Replace ```example.com``` in ```dockerized-wordpress/docker-compose.yml``` with
   with your own domain.