# 

# CRUD

**Note:** We are removed this terminal based CRUD Builder. We  moved to GUI builder. For GUI documentation

[click here](https://www.gitbook.com/book/lorvent/josh/edit#/edit/master/gui-crud.md?_k=m4emhc)

you can generate CRUD using below command

for example: to generate books model with title, author, description fields

please run

```\`php
php artisan crud:gen book --fields="string:title,string:author,text:description"
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

## other field types

we will be updating CRUD continously and you can expect other field types in coming days

## planned field types

* select2
* icheck



