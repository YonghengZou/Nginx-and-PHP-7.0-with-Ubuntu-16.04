# Nginx-and-PHP-7.0-with-Ubuntu-16.04
Install and configure Nginx and PHP 7.0 with Ubuntu 16.04


1. sudo apt-get update

2. sudo apt=get install nginx

3. curl localhost （verify nginx has been installed on the host）

4. sudo apt-get install php-fpm

5. sudo nano /etc/php/7.0/fpm/php.ini
    when you write this command line, you will enter a document and then find cgi.fix_pathinfo to make it equal 0

6. sudo systemctl restart php7.0-fpm

7. sudo nano /ect/nginx/sites-available/default
    (1) add index.php in this line --> index index.html index.htm index.nginx-debian.html;
    (2) location ~ \.php${
              include snippets/fastcgi-php.conf;
              fastcgi_pass unix:/run/php/php7.0-fpm.sock;
              }
    (3) location ~ /\.ht{
    
              deny all:
              }
     
8. sudo nginx -t

9. sudo systemctl reload nginx

YOU GOT IT!
