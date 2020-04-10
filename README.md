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
5. Run ```docker-compose up -d```
6. Check that your certificates have been mounted to the ```webserver``` container:
   ```
   docker-compose exec webserver ls -la /etc/letsencrypt/live
   ```
   If your certificate requests were successful, you will see output like this:
   ```
   total 16
   drwx------    3 root     root          4096 May 10 15:45 .
   drwxr-xr-x    9 root     root          4096 May 10 15:45 ..
   -rw-r--r--    1 root     root           740 May 10 15:45 README
   drwxr-xr-x    2 root     root          4096 May 10 15:45 example.com
   ```
7. Replace the ```--staging``` flag in ```dockerized-wordpress/docker-compose.yml``` 
   with the ```--force-renewal``` flag.
8. Recreate the ```certbot``` container.
   ```
   docker-compose up --force-recreate --no-deps certbot
   ```
9. Enable SSL in our Nginx configuration:
   ```
   mv nginx_ssl.conf nginx-conf/nginx.conf
   ```
10. Replace (again) ```example.com``` in ```nginx-conf/nginx.conf```with your own domain.
11. Run ```docker-compose up -d --force-recreate --no-deps webserver```