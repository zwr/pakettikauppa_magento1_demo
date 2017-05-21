# Magento 1 demo shop for Pakettikauppa

## Admin account

Admin path: /admin
Username: pkdemo
Password: pkdemo1

## Preconditions

1. PHP 5.6 or other compatible with Magento 1.9
2. PHP mcrypt module
3. Nginx (you can use something else too, but these instructions are for nginx)
4. MySQL

## Deployment

* Clone the repo somewhere, which will become root path
* Copy dev/nginx/zk.conf to the nginx server configuration
* In the copied file, replace at least server_name and root directives
* Configure MySQL: create a database and create a user with all rights to it:

        mysql> create database pkdemo;
        Query OK, 1 row affected (0.01 sec)

        mysql> create user 'pkdemo'@'localhost' identified by 'pkdemo';
        Query OK, 0 rows affected (0.01 sec)

        mysql> grant all privileges on pkdemo.* to 'pkdemo'@'localhost';
        Query OK, 0 rows affected (0.00 sec)

* Restore the database

        mysql -upkdemo -ppkdemo -ADpkdemo < dev/db/db.sql

An empty shop should appear now when correct host is hit in a browser.


