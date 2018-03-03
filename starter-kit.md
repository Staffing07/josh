# Josh Admin Starter kit

### Installation:

Starter kit installation is same as Josh regular installation. Please follow the [documentation](https://lorvent.gitbooks.io/josh/content/laravel-55.html)

### Adding Pages

Including pages is very easy to do. Follow the below instructions.

We added a blank page for adding new page. you can find the blank page at resources/views/blank.blade.php.

write the content inside  @section\('content'\) & @stop

```
@section('content')
    //Write Body here 
@stop
```

If need to add any external JS and css links. look at below code

```
@section('header_styles')
    // Add CSS links here
@stop

@section('footer_scripts')
    // Add JS links here
@stop
```

Don't forgot add Page to left menu\(resources/views/layouts/\_left\_menu.blade\).

These things are enough for adding a new page.

### Adding Pages from Josh App

If you want to add a page from Josh main theme. need to copy the related files to starter kit.

Here we taken an form builder as example.

We will explain how to integrate form builder page from Josh app into starter kit.

first we should find what are the plugins are used in form builder page.

Form builder needs bootstrap form builder Jquery plugin. So, you have to add it in bower.json .

1.Add bootstrap form builder jquery plugin to bower dependencies in bower.json

```
"bootstrap-form-builder": "https://github.com/sajidshah/bootstrap3_formbuilder.git",
```

1. Add paths in webpack.mix.js

```
'bootstrapFormBuilder': vendors + 'bootstrap-form-builder/',
```

and add mix.copy

```
//bootstrap-form-builder
mix.copy(paths.bootstrapFormBuilder + 'assets3',  destVendors + 'bootstrap-form-builder', false);
```

Then run bower install & npm run dev

```
bower install

npm run dev
```

1. Copy the "form\_builder.blade.php" file from Josh app\(Laravel 5.5 fresh/laravel5.5/views/resources/admin/form\_builder.blade.php\) to  starterKit/resources/views 

open the form\_builder.blade.php file and check what css and js link are used copy that files to starter kit from Josh App\(resources\).

and add mix.copy in webpack.mix.js.

in this file "formbuilder.css" file used, So i should add in webpack.mix.js and run "npm run dev"

```
<link href="{{ asset('assets/css/pages/formbuilder.css') }}" rel="stylesheet" />
```

```
mix.copy(srcCss + 'pages/formbuilder.css', destCss + 'pages');
```

1. Open the page in browser [http://starterkit/public/form\_builder](http://starterkit/public/form_builder)

   check page is working or not.

1. add  page link to left menu  in \_left\_menu.blade.php

```
<li {!! (Request::is('form_builder') ? 'class="active"' :'') !!>
   <a href="{{ URL::to('admin/form_builder') }}">
       <i class="livicon" data-name="home" data-size="18" data-c="#418BCA" data-hc="#418BCA" data-loop="true"></i>
       <span class="title">Form Builder</span>
   </a>
</li>
```

These steps are enough for form builder. You want to add any other module from josh app, you should check what plugins and  css, js files are used in that page and add it into starter kit.



### Adding Features from Josh App

Adding Features is similar to adding a page from josh.follow as the above steps and need to add few more things, like controllers, migrations, models etc.

First you have to find what package they are used in Josh App. 

Here we adding **Laravel Charts**.   

We are using **ConsoleTv** Charts package. Let find the package name and version at composer.json file in Josh App and add it into starter kit.  

open composer.json and add it

```
 "require": {
     ......
     "consoletvs/charts": "5.*",
     ......
}
```

Run **composer install**

Add the following service provider to the array in: `config/app.php`

```
ConsoleTVs\Charts\ChartsServiceProvider::class,
```

Add the following alias to the array in:`config/app.php`

```
'Charts'=>ConsoleTVs\Charts\Facades\Charts::class,
```

 Add Routes in web.php file

```
/*laravel example routes*/
#Charts
Route::get('laravel_chart','ChartsController@index')->name('laravel_chart');

Route::get('database_chart','ChartsController@databaseCharts')->name('database_chart');
```

Copy the which controllers are used, here they used ChartsController.php. Let's copy the charts controller to starter kit\(App/Http/Controllers\).   

And also copy the charts folder from josh mail App \(resources/views/vendor/charts\) to starterkit/resources/views/vendor/charts.

These steps are enough for adding laravel charts.

