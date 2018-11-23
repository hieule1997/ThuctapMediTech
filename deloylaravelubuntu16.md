### Install mysql
```
apt-get -y install mysql-server mysql-client

```
### Config mysql
```
mysql_secure_installation
```
### Kiểm tra version 
```
mysql --version
```
### Install apache2
``` 
apt-get -y install apache2
```
### bật mod
```
a2enmod rewrite
```
### Resret apache
```
systemctl restart apache2
```
### Install php 7.2
```
apt-add-repository ppa:ondrej/php
apt-get update

apt-get -y install php7.2 libapache2-mod-php7.2
systemctl restart apache2
cd /var/www//html/
apt show php-cli
 apt install php-cli
apt install php7.2-bcmath
nano /var/www/html/info.php

    - Thêm vào file info.php 
            <?php
                phpinfo()
            >
chown www-data:www-data /var/www/html/info.php
apt-cache search php7.2
apt-get -y install php7.2-mysql php7.2-curl php7.2-gd php7.2-intl php-pear php-imagick php7.2-imap php-memcache  php7.2-pspell php7.2-recode php7.2-sqlite3 php7.2-tidy php7.2-xmlrpc php7.2-xsl php7.2-mbstring php-gettext

systemctl restart apache2
apt-get -y install php7.2-opcache php-apcu

 systemctl restart apache2

apt update

apt install phpmyadmin php-mbstring php-gettext

phpenmod mbstring

systemctl restart apache2

mysql -u root -p

mysql> SELECT user,authentication_string,plugin,host FROM mysql.user;

mysql> ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';

mysql> SELECT user,authentication_string,plugin,host FROM mysql.user;
Định cấu hình truy cập mật khẩu cho người dùng MySQL chuyên dụng
mysql
mysql> CREATE USER 'sammy'@'localhost' IDENTIFIED BY 'password';
mysql> GRANT ALL PRIVILEGES ON *.* TO 'sammy'@'localhost' WITH GRANT OPTION;
mysql> exit
sudo nano /etc/apache2/apache2.conf
Sau đó thêm dòng sau vào cuối tập tin:
#include phpmyadmin
Include /etc/phpmyadmin/apache.conf
systemctl restart apache2
apt-get install -y git curl wget

 git clone https://github.com/hieule1997/projectnhanhieu

 sudo chgrp -R www-data /var/www/html/projectnhanhieu/

sudo chmod -R 775 /var/www/html/projectnhanhieu/storage

cd /etc/apache2/sites-available

nano nhanhieu.conf

        <VirtualHost *:80>
        ServerName nhanhieu.comparepricetech.club
        ServerAdmin nhanhieu.comparepricetech.club
        DocumentRoot /var/www/html/projectnhanhieu/public
        <Directory /var/www/html/projectnhanhieu>
        AllowOverride All
        </Directory>
        ErrorLog ${APACHE_LOG_DIR}/error.log
        CustomLog ${APACHE_LOG_DIR}/access.log combined
        </VirtualHost>


a2dissite 000-default.conf

service apache2 reload

a2ensite nhanhieu.conf

service apache2 reload

a2enmod rewrite

service apache2 restart 

php composer-setup.php --install-dir=bin --filename=composer  
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" 

php -r "if (hash_file('sha384', 'composer-setup.php') === '93b54496392c062774670ac18b134c3b3a95e5a5e5c8f1a9f115f203b75bf9a129d5daa8ba6a13e2cc8a1da0806388a8') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"

 php composer-setup.php

 php -r "unlink('composer-setup.php');"

 nano .env
 cấu hình file .env
cd /var/www/html/

apt install composer

composer update

php artisan cache:clear



```


