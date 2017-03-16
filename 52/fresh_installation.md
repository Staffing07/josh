# Fresh Installation

This zip file contains all laravel files integrated with josh, however you need to perform following steps to get vendors etc.

#### Get Composer packages

`composer install`

#### permissions

```
chmod -R 755 storage

chmod 755 bootstrap/cache
```

If you are on linux/ mac you can run below command to chown it.

```
chown -R www-data /var/www
```

#### database credentials

open `.env` and modify database details with yours

#### add tables to databaes

`php artisan migrate`

#### add admin to users table

`php artisan db:seed --class=AdminSeeder`

#### compile assets

> If you don't have good knowledge on nodejs and npm, you can copy public folder files from codecanyon's downloaded files.

Make sure you have [nodejs](https://nodejs.org) installed in your system

install gulp, bower globally

`npm install -g gulp bower`

install local packages

`npm install`

install sass globally

`npm install -g node-sass`

get bower components

`gulp bower`

move assets to public

`gulp`

# Congratulations

open your website and now it should be fully working :\)

