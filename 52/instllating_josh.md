# Installing JOSH

Please follow installation steps mentioned in "Laravel 5.1" but with following change in composer.

## composer changes
We Assume, your composer already includes ```"laravel/framework": "5.2.*",```

### laravelcollective/html

Now, instead of ~~```"laravelcollective/html": "5.1.*",```~~ 

Use ```"laravelcollective/html": "5.2.*",```


Finally your composer.json, ```require``` array should have these

```
"laravelcollective/html": "5.2.",
"cartalyst/sentinel": "2.0.",
"cviebrock/eloquent-sluggable": "dev-master",
"cviebrock/eloquent-taggable": "~2.0.0",
"yajra/laravel-datatables-oracle": "~5.0"
```

## Routes changes

We need to wrap all routes in routes.php with ```web``` middleware, like below

```php
Route::group(['middleware' => 'web'], function () {
    
    /*
|--------------------------------------------------------------------------
| Application Routes
|------------------------------------------------------------------


...
//all other routes
...

Route::get('{name?}', 'JoshController@showFrontEndView');
# End of frontend views

});
```

