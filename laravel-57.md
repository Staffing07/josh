We have split this installation into 3 parts

* Pre-requisites 
* Installation
* after setup

# Pre-requesites

In order to use JOSH which is a developer oriented product, you should have basic idea of following tools and make sure they are installed in your sytem.

**Windows Users** If you don't want to install all of them manually, please download [laragon](https://laragon.org/)

1. Git 

you can check if you have git by running `git -v` in terminal, if you don't have it...you can get it from git-scm.com

or on \*nix system, you can install by running `apt-get install git` command

1. nodejs

you can check if you have nodejs installed or not by running `nodejs -v` in terminal, if you don't have it... you can get it from nodejs.org

for \*nix system, find instructions here [https://nodejs.org/en/download/package-manager/](https://nodejs.org/en/download/package-manager/)

1. yarn

you can check for yarn existence by running `yarn -v` in terminal, if you don't have it, you can get from their their website [https://yarnpkg.com](https://yarnpkg.com) and follow instructions mentioned there

1. composer

you can check for composer existence by running `composer -v` in terminal and if you don't have it, get it from getcomposer.org

# Installation

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

#### compiling assets

`yarn install`

`npm run dev`

if everything compiles successfully, by now you should have a working website

you can access your website at http://URL/public \(if not using virtualhosts\) or http://URL \(if using virtualhosts\)  
and you can access admin section by going to http://URL/public/admin or http://URL/admin respectively.



# After setup

Still we need to get some keys and setup things to make sure josh is working properly

1. CRUD folders permission

our GUI crud generator writes new files to many folders and if you are on \*nix, you need to adjust permissions

please check https://lorvent.gitbooks.io/josh/content/gui-crud.html for details

2. Recaptcha keys

Josh has Google recaptcha feature for signup, login etc

so you need to get keys from https://www.google.com/recaptcha/admin and paste them in .env file for keys `GOOGLE_RECAPTCHA_KEY` and `GOOGLE_RECAPTCHA_SECRET`

3. Analytics keys

Josh admin panel can display Google analytics data right in your josh dashboard without leaving site, for which you need to get json file from google site and set analytics view

follow https://github.com/spatie/laravel-analytics\#how-to-obtain-the-credentials-to-communicate-with-google-analytics for more details

4. Google map keys

you need to get google maps keys for maps pages to work, if you don't need these pages, you can ignore it.



