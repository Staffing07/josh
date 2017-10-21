# CRUD

You can generate CRUD using GUI Builder without run a single command.

If you want to use GUI builder simply fill the form i.e model name, table name and table fields.

## Folder Permissions

Give write permissions to models, controllers, views, routes and migrations

```\`php
chmod -R 777 ./routes/web_builder.php

chmod -R 777 ./routes/web.php

chmod -R 777 ./resources/views    

chmod -R 777 ./app/Models/    

chmod -R 777 ./app/Http    

chmod -R 777 ./database/    


```

If you want just model and controller then execute

```\`php
php artisan crud:gen book
```

when you don't pass fields, it will just create model and controller

## available field types

* string - this will create a varchar in database, input field for views
* text - this will create a text in daabase and textarea for views
* password - this will create varchar in database, password field for views
* email - this will create varchar in database, email field for views
* radio
* checkbox
* file

all others will be treated as varchar in database and respected field type will be created for views

ex: if you pass 'radio' then in views, input type="radio" will be created

## 

## 



