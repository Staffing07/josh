#CRUD

CRUD generator is a new feature to JOSH

Using CRUD You can generate

* Model
* Controller
* views
* routes
* menu
* migration

or **ALL** of them


#### Video

Watch below video for a good demo

{% youtube %}https://www.youtube.com/watch?v=OnQPnFO5Quo{% endyoutube %}



#### Installation

all files are provided in downloaded folder.

open config/app.php and in providers array, add
````php
    'App\Providers\JoshCrudGeneratorServiceProvider',
````

**register custom_routes.php**

since we store our routes in custom_routes.php, we need to add it in route server provide

open app/Providers/RouteServiceProvider.php

in ````map```` function add ````require app_path('Http/custom_routes.php');```` before default roues

so **finally** ````map```` method  should look like

````
public function map(Router $router)
    {
        $router->group(['namespace' => $this->namespace], function ($router) {
            require app_path('Http/custom_routes.php');
            require app_path('Http/routes.php');
        });
    }
````    


#### Usage

[Please click here for usage info](http://lorvent.gitbooks.io/josh/content/crud.html)


## reporting bugs, suggestions

since its new feature, please feel free to report bugs, suggestions at [issues](https://bitbucket.org/lorvent/josh_laravel51/issues) section

## early access

if you would like to have early access to new features, please [contact us](http://codecanyon.net/user/jyostna#contact) with your purchase code  and your email address and we will add you to repo.
