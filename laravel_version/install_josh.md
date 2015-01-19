# Install Josh
We try to minimise use of third party packages but <code>sentry</code> is one package which provides many features out of box so we use it.

### Setup sentry
**Add Sentry to composer**

Open your composer.json file and add the following to the require array:

<code>"cartalyst/sentry": "2.1.*",</code>

now in your command prompt run <code>composer update</code> and all required files will be added

**Add sentry service provider**

Now, we need to add sentry service provider to make use of it.

Open <code>app/config/app.php</code> and add following lines

In the <code>$providers</code> array add the following service provider

<code>'Cartalyst\Sentry\SentryServiceProvider',</code>

In the <code>$aliases</code> array add the following facade

<code>'Sentry' => 'Cartalyst\Sentry\Facades\Laravel\Sentry',</code>

Now we need to add user, groups etc tables to database, to do so in your command prompt, execute following code

```

php artisan migrate --package=cartalyst/sentry

```


Now we need to publish config, so that you can edit configuration, if needed

Excecute following command in command prompt/terminal
```

php artisan config:publish cartalyst/sentry

```

please headover to [sentry website](https://cartalyst.com/manual/sentry) to learn more about it

### Add admin user
As database tables have been setup, we need to add admin user to be able to login into adminCP.

Run following command in your command prompt

```
php artisan db:seed

```

**A default admin user with user with username admin@admin.com and password admin will be created**

Note: Optional:If you wish to use a different username or password, please open <code>app\database\seeds\AdminSeeder.php</code> and edit values around lines 14-18

### Adding extra fields to users table
We have added many other fields to <code>users</code> table, you can add all those fields by executing below command in command prompt/terminal

<code>php artisan migrate</code>

Note: please check all files in <code>app/database/migrations</code> to know what fields are being added.
