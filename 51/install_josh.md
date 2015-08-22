# Install Josh
We use good number of packages to provide great functionality without re-inventing wheel.

We need to add those packages to <code>composer.json</code>, publish vendor configurations and finally do migrations.

####packages used


| Package name | repo | manual |
| -- | -- | -- |
| cartalyst/sentinel | [repo](https://github.com/cartalyst/sentinel) | [manual](https://cartalyst.com/manual/sentinel/2.0) |
| laravelcollective/html | [repo](https://github.com/LaravelCollective/html) | [manual](http://laravelcollective.com/docs/5.1/html) |



---

### Delete existing migration files

Since we are not relying on default migration tables, please remove following two files from <code>database/migrations</code> folder

```
2014_10_12_000000_create_users_table.php
2014_10_12_100000_create_password_resets_table.php
```

Otherwise you will get error at later stage of installation.


---

### Install Packages

** Add Package to composer**

Now add above mentioned packages in ```composer.json``` in ```require``` array

````
"cartalyst/sentinel": "2.0.*",
"laravelcollective/html": "5.1.*"
````

** Add service providers **

Open <code>config/app.php</code> and add following lines in the <code>$providers</code> array 

````php
Cartalyst\Sentinel\Laravel\SentinelServiceProvider::class,
Collective\Html\HtmlServiceProvider::class,
````

In the <code>$aliases</code> array add  following facades
````php
'Activation' => Cartalyst\Sentinel\Laravel\Facades\Activation::class,
'Reminder'   => Cartalyst\Sentinel\Laravel\Facades\Reminder::class,
'Sentinel'   => Cartalyst\Sentinel\Laravel\Facades\Sentinel::class,
'Form' => Collective\Html\FormFacade::class,
'Html' => Collective\Html\HtmlFacade::class,
````

** publish vendors **

now we need to publish vendor files so that they will publish config files, migrations.

Excecute following command in command prompt/terminal
```

php artisan vendor:publish

```

Now we need to add user, groups etc tables to database, to do so in your command prompt, execute following code

```

php artisan migrate

```

Note: please check all files in <code>database\migrations</code> to know what fields are being added.




** setting up config to use our model**

since we have different requirements (extra fields in users table), we need to change sentinel config to use our user Model,

to do that open <code>config/cartalyst.sentinel.php</code>

at line 56, find

````
'model' => 'Cartalyst\Sentinel\Users\EloquentUser',
````

replace it with

````
'model' => 'App\User',
```

** Add admin user**

As database tables have been setup, we need to add admin user to be able to login into adminCP.

Run following command in your command prompt

```
php artisan db:seed --class=AdminSeeder

```

*A default admin user with user with username admin@admin.com and password admin will be created*

Optional: If you wish to use a different username or password, please open <code>database\seeds\AdminSeeder.php</code> and edit values around lines 14-18


** upload directory permissions **

user's profile pics will be uploaded into <code>public/uploads/users</code>

so we need to provide write access for that folder

to do so, please run following command in your command prompt/terminal

```
chmod 775 public/uploads/users
chmod 775 public/uploads/blog
```
###Congratulations! You are ready to rock the world!!


---


