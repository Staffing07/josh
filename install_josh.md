# Install Josh
We need to install following packages, run migrations and database seeding.

### Setup HTML package

Laravel 5 doesn't come with HTML,FORM package by default,

if you want to use it... we need to add package manually

Since we use it in many places, we have to add it to our composer.json

** Add Package to composer**

open your composer.json file and add the following to the require array:

<code>""illuminate/html": "~5.0","</code> then in terminal/cmd run <code>composer update</code>

** Add service providers **

Open <code>config/app.php</code> and add following lines

In the <code>$providers</code> array add the following service provider

<code>'Illuminate\Html\HtmlServiceProvider',</code>

In the <code>$aliases</code> array add  following facades

<code>'Form'      => 'Illuminate\Html\FormFacade',</code>

<code>'Html'      => 'Illuminate\Html\HtmlFacade',</code>

### Setup sentry
**Add Sentry to composer**

Open your composer.json file and add the following to the require array:

<code>"cartalyst/sentry": "dev-feature/laravel-5",</code>

now in your command prompt run <code>composer update</code> and all required files will be added

**Add sentry service provider**

Now, we need to add sentry service provider to make use of it.

Open <code>config/app.php</code> and add following lines

In the <code>$providers</code> array add the following service provider

<code>'Cartalyst\Sentry\SentryServiceProvider',</code>

In the <code>$aliases</code> array add the following facade

<code>'Sentry' => 'Cartalyst\Sentry\Facades\Laravel\Sentry',</code>

Now we need to add user, groups etc tables to database, to do so in your command prompt, execute following code

```

php artisan migrate --path=vendor/cartalyst/sentry/src/migrations

```


Now we need to publish config, so that you can edit configuration, if needed

Excecute following command in command prompt/terminal
```

php artisan vendor:publish

```

please headover to [sentry website](https://cartalyst.com/manual/sentry) to learn more about it

### Add admin user
As database tables have been setup, we need to add admin user to be able to login into adminCP.

Run following command in your command prompt

```
php artisan db:seed

```

**A default admin user with user with username admin@admin.com and password admin will be created**

Note: Optional:If you wish to use a different username or password, please open <code>database\seeds\AdminSeeder.php</code> and edit values around lines 14-18

### Adding extra fields to users table
We have added many other fields to <code>users</code> table, you can add all those fields by executing below command in command prompt/terminal

<code>php artisan migrate</code>

Note: please check all files in <code>database/migrations</code> to know what fields are being added.
