> This is a simplefied documentation according to **MY NEEDS** and in order to facilitate **MY LIFE** when programming in Laravel. Yet you must check the complete [oficial documentation][documentation]

### Summary

- <a href="#program.installation">Programs Installation</a>
- <a href="#project.create">Crate project</a>
  - <a href="#project.view">Create view</a>
- <a href="#project.controller">Create controller</a>
  - <a href="#project.controller.function">Controller functions</a>
  - <a href="#project.controller.resource">Controller with resource</a>
- <a href="#project.routing">Routing</a>
  - <a href="#project.routing.resource">Route Resource</a>
- <a href="#project.view.components">Create component</a>
- <a href="#project.db.get">Retrieving data from database</a>
- <a href="#">a</a>
- <a href="#project.cloning">Cloning project</a>

<hr>

### <span id="program.installation">Programs installation</span>

- Mandatory
    - [Composer][composer]
    - [Laravel][laravel]

- Recommended
    - [PHPStorm][phpstorm]

- Optional
    - [VSCode][vscode]

<hr>

> ### <span id="project.create">[Creating project][project.create]</span>

- Via Laravel Installer

<small style="color:grey;font-size:13px"><span style="color:	#000">Requirement</span>: composer global require laravel/installer;</small>

```cmd
    laravel new <\project_name>
```

- Via Composer

```cmd
    composer create-project laravel/laravel <project_name>
```

<hr>

> ### <span id="project.view">[Creating view][project.view]</span>

<small style="color:grey;font-size:13px">create new file on <span style="color:#000">resources/views/</span></small>

```dir
    <file_name>.blade.php
```

#### [Extending a master layout][project.view.extending]

<small style="color:grey;font-size:13px">create new view and <span style="color:#000">extend it on any other view</span></small>

```blade
@extends('<\view_path>')
```

<hr>

> ### <span id="project.controller">[Creating controller][project.controller]</span>

```cmd
    php artisan make:controller <singular_name>Controller
```

<small style="color:grey;font-size:13px">E.g. php artisan make:controller <span style="color:#000">Book</span>Controller</small>

#### <span id="project.controller.function">[Controller functions][project.controller.function]</span>

<small style="color:grey;font-size:13px">add new function to <span style="color:#000">app/Http/Controllers/<\controller></span></small>

```
    public function index() { ... }
```

#### <span id="project.controller.resource">[Controller with resource][project.controller.resource]</span>

```cmd
    php artisan make:controller <singular_name>Controller --resource --model=<model_name>
```

<small style="color:grey;font-size:13px">E.g. php artisan make:controller <span style="color:#000">Book</span>Controller<span style="color:#000">--resource --model=Book</span></small>

<hr>

> ### <span id="project.routing">[Routing][project.routing]</span>

<small style="color:grey;font-size:13px">add new route to <span style="color:#000">routes/web.php</span></small>

Route::get($uri, $callback);
Route::post($uri, $callback);
Route::put($uri, $callback);
Route::patch($uri, $callback);
Route::delete($uri, $callback);
Route::options($uri, $callback);


#### <span id="project.routing.resource">[Route Resource][project.routing.resource]</span>

<small style="color:grey;font-size:13px">create a Controller with <span style="color:#000">--resource</span> param, then use <span style="color:#000">Route::resource</span> on <span style="color:#000">routes/web.php</span></small>
<small style="color:grey;font-size:13px"><span style="color:#000"></span>E.g.: php artisan make:controller BookController <span style="color:#000">--resource</span></small>

```
    Route::resource('filmes', 'App\Http\Controllers\MovieController')   // URI
    ->names('movie')                                                    // <example>.index
    ->parameters(['filmes' => 'movie']);                                // '{example}' => 'movie'
```

<small style="color:grey;font-size:13px"><span style="color:#000">index</span> - Show all (listing)</small>
<small style="color:grey;font-size:13px"><span style="color:#000">create</span> - Insert form</small>
<small style="color:grey;font-size:13px"><span style="color:#000">store</span> - Persist info on DB</small>
<small style="color:grey;font-size:13px"><span style="color:#000">show</span> - One record (details)</small>
<small style="color:grey;font-size:13px"><span style="color:#000">edit</span> - Editing form</small>
<small style="color:grey;font-size:13px"><span style="color:#000">update</span> - Persist edited info o n DB</small>
<small style="color:grey;font-size:13px"><span style="color:#000">destroy</span> - Delete info</small>

<hr>

#### <span id="project.view.components"></span>[Create component][project.view.component]

<hr>

#### <span id="project.db.get">[Retrieving data from database][first]

<hr>

> public function show($id) { ... } //shorter way
> same as
> public function show(Product $product)
{ 
    $product = Product::findOrFail($id); //dont need to
}

> use Illuminate\Support\Facades\Route;
> Change laravel's URI pattern
> Route::resourceVerbs(['create' => 'adicionar', 'edit' => 'editar']);


<hr>

> ### <span id="project.cloning">[Setting Laravel enviroment after cloning project from GitHub][project.cloning]</span>

- Clone your project

```cmd
    git clone <\URL>
```

- Go to the folder application using cd command on your cmd or terminal

```cmd
    cd <\folder_name>
```

- Run composer install on your cmd or terminal

```cmd
    composer install
```

- Copy .env.example file to .env on the root folder. You can type copy .env.example .env if using command prompt Windows or cp .env.example .env if using terminal, Ubuntu

```
    copy .env.example .env
```

- Open your .env file and change the database name (DB_DATABASE) to whatever you have, username (DB_USERNAME) and password (DB_PASSWORD) field correspond to your configuration.
> By default, the username is root and you can leave the password field empty. (This is for **Xampp**)
> By default, the username is root and password is also root. (This is for **Lamp**)

- Run the following commands

<small style="color:grey;font-size:13px"><span style="color:	#000">key:generate</span> - Used to define a new key on .env file, after cloning a Laravel project;</small>

```cmd
    php artisan key:generate
```

<small style="color:grey;font-size:13px"><span style="color:	#000">migrate</span> - Used to run database tables</small>

```cmd
    php artisan migrate
```

<small style="color:grey;font-size:13px"><span style="color:	#000">serve</span> - Used to start a server</small>

```cmd
    php artisan serve
```

- Go to localhost:8000

### Using Image Intervantion

> Used to resize image once uploaded

```cmd
    composer require intervention/image
```

Register package into $providers
on config/app.php

Intervention\Image\ImageServiceProvider::class

$aliases

'Image' => Intervention\Image\Facades\Image::class
// in order to make path shorter

use Image;
// Controller


[documentation]: https://laravel.com/docs/
[composer]: https://getcomposer.org/
[laravel]: https://laravel.com/
[phpstorm]: https://www.jetbrains.com/phpstorm/
[vscode]: https://code.visualstudio.com
[project.create]: https://laravel.com/docs/8.x/installation#installation-via-composer
[project.view]: https://laravel.com/docs/8.x/views#creating-and-rendering-views
[project.view.extending]: https://laravel.com/docs/8.x/blade#extending-a-layout
[project.controller]: https://laravel.com/docs/8.x/controllers#basic-controllers
[project.controller.resource]: https://laravel.com/docs/8.x/controllers#resource-controllers
[project.controller.function]: https://laravel.com/docs/8.x/routing#the-default-route-files
[project.routing]: https://laravel.com/docs/8.x/routing#basic-routing
[project.routing.resource]: https://laravel.com/docs/8.x/controllers#resource-controllers
[project.view.component]: https://laravel.com/docs/8.x/blade#components
[project.cloning]: https://stackoverflow.com/questions/38602321/cloning-laravel-project-from-github