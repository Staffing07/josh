# 5.5 Installation

The zip file contains all laravel files integrated with josh, however you need to perform following steps to get vendors etc.

#### Get Composer packages

`composer install`

#### permissions

```
chmod -R 775 storage

chmod 775 bootstrap/cache
```

If you are on linux/ mac you can run below command to chown it.

```
chown -R www-data /var/www
```

#### database credentials

```
cp .env.example .env
```

open `.env` and modify database details with yours

#### Generate Key

```
php artisan key:generate
```

#### add tables to databaes

`php artisan migrate`

#### add admin to users table

`php artisan db:seed --class=AdminSeeder`

#### compile assets

> If you don't have good knowledge on nodejs and npm, you can copy public folder files from codecanyon's downloaded files

**Note : **The above step is completely optional , if you are not comfortable with this, you can skip it and perform the below steps, still it works fine.

Make sure you have [nodejs](https://nodejs.org) installed in your system with minimum version `6.10.0`,

you can check installed version by running `node -v` command in terminal.

If you are having older version, please install latest version from [nodejs.org](http://nodejs.org/)

For laravel 5.5 , the minimum version of php required is 7.0.0 and

the following php extensions are rquired

* PHP &gt;= 7.0.0
* OpenSSL PHP Extension
* PDO PHP Extension
* Mbstring PHP Extension
* Tokenizer PHP Extension
* XML PHP Extension

install local packages

`yarn install`

get bower components

`bower install`

move assets to public

`npm run dev`

** Note:** If bower gives warning that you are running as administrator, please run the command `bower install --allow-root`

# Congratulations

open your website and now it should be fully working :\)

