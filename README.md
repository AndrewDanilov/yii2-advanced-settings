# Yii2 advanced template settings
Misc configs and settings for yii2-advanced template

## Install Project

First, with Composer installed, you can install the application using the following command:

    composer create-project --prefer-dist yiisoft/yii2-app-advanced yii-application

The command installs the advanced application in a directory named `yii-application`. You can choose a different
directory name if you want.

## Initialize environment

Initialize your app with commands

    cd yii-application
    php init

## Configure your app

Configure your server and app as shown in config files of this repository.

## Database setup

This step is optional. You can create database, database user and setup permissions for it.

### Example DB creation process for MySQL server

sudo mysql -uroot -p
```mysql
# Create database
CREATE DATABASE mydatabase CHARACTER SET utf8 COLLATE utf8_general_ci;
# Create database user
CREATE USER 'username'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
# Setup user privileges
GRANT ALL PRIVILEGES ON mydatabase.* TO 'username'@'localhost';
# Renew privileges
FLUSH PRIVILEGES;
```

### Example DB creation process for MariaDB server

sudo mysql -uroot -p
```mysql
# Create database
CREATE DATABASE mydatabase CHARACTER SET utf8 COLLATE utf8_general_ci;
# Create database user
CREATE USER 'username'@'localhost' IDENTIFIED BY 'password';
# Setup user privileges
GRANT ALL PRIVILEGES ON mydatabase.* TO 'username'@'localhost';
# Renew privileges
FLUSH PRIVILEGES;
```

## Setup yii db config file

If you use database in your app, set it up in `common/config/main-local.php` config file

```php
return [
    'components' => [
        'db' => [
            'class' => 'yii\db\Connection',
            'dsn' => 'mysql:host=localhost;dbname=mydatabase',
            'username' => 'username',
            'password' => 'password',
            'charset' => 'utf8',
        ],
        // ...
    ],
];
```

## Run initializing migrations

    php yii migrate

## Site extensions set example

For creating full-featured customizable cms-like site with admin-panel and page templates, you can
use this set of extensions:

* [andrewdanilov/yii2-admin-panel](https://github.com/AndrewDanilov/yii2-admin-panel)
* [andrewdanilov/yii2-site-data](https://github.com/AndrewDanilov/yii2-site-data)
* [andrewdanilov/yii2-custom-pages](https://github.com/AndrewDanilov/yii2-custom-pages)

If you creating shop, add this extension to that set:

* [andrewdanilov/yii2-shop](https://github.com/AndrewDanilov/yii2-shop)
