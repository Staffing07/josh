# Install Josh
We need to install following packages, run migrations and database seeding.

### Delete existing migration files

Since we are not relying on default migration tables, please remove following two files from <code>database/migrations</code> folder

```
2014_10_12_000000_create_users_table.php
2014_10_12_100000_create_password_resets_table.php
```

Otherwise you will get error at later stage of installation.

### Setup HTML package

Laravel 5 doesn't come with HTML,FORM package by default,

if you want to use it... we need to add package manually

Since we use it in many places, we have to add it to our composer.json

** Add Package to composer**

open your composer.json file and add the following to the require array:

<code>"laravelcollective/html": "5.1.*"</code> then in terminal/cmd run <code>composer update</code>

** Add service providers **

Open <code>config/app.php</code> and add following lines

In the <code>$providers</code> array add the following service provider

<code>Collective\Html\HtmlServiceProvider::class,</code>

In the <code>$aliases</code> array add  following facades

<code>'Form' => Collective\Html\FormFacade::class,</code>

<code>'Html' => Collective\Html\HtmlFacade::class,</code>

### Setup sentinel
**Add Sentinel to composer**

Open your composer.json file and add the following to the require array:

<code>"cartalyst/sentinel": "2.0.*"</code>

now in your command prompt run <code>composer update</code> and all required files will be added

**Add sentinel service provider**

Now, we need to add sentinel service provider to make use of it.

Open <code>config/app.php</code> and add following lines

In the <code>$providers</code> array add the following service provider

<code>'Cartalyst\Sentinel\Laravel\SentinelServiceProvider',</code>

In the <code>$aliases</code> array add the following facade

````
'Activation' => 'Cartalyst\Sentinel\Laravel\Facades\Activation',
'Reminder'   => 'Cartalyst\Sentinel\Laravel\Facades\Reminder',
'Sentinel'   => 'Cartalyst\Sentinel\Laravel\Facades\Sentinel',
````

Now we need to add user, groups etc tables to database, to do so in your command prompt, execute following code

```

php artisan migrate

```

Note: please check all files in <code>database\migrations</code> to know what fields are being added.


Now we need to publish config, so that you can edit configuration, if needed

Excecute following command in command prompt/terminal
```

php artisan vendor:publish

```

please headover to [sentinel website](https://cartalyst.com/manual/sentinel) to learn more about it

** Use our user model for sentinel **

open 

### Add admin user
As database tables have been setup, we need to add admin user to be able to login into adminCP.

Run following command in your command prompt

```
php artisan db:seed

```

**A default admin user with user with username admin@admin.com and password admin will be created**

Optional: If you wish to use a different username or password, please open <code>database\seeds\AdminSeeder.php</code> and edit values around lines 14-18


### upload directory permissions

user's profile pics will be uploaded into <code>public/uploads/users</code>

so we need to provide write access for that folder

to do so, please run following command in your command prompt/terminal

```
chmod 777 public/uploads/users
```
