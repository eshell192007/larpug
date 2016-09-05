[![](media/pug128.png)](/pugjs/pug)
![](media/and128.png)
[![](media/laravel128.png)](/http://laravel.com)
![](media/plus128.png)
[![](media/lumen128.png)](/http://lumen.laravel.com)

Allows you to use native [Pug](/pugjs/pug) (formerly [Jade](https://github.com/scrooloose/syntastic/pull/1704)) seamlessly in [Laravel 5](http://laravel.com) and [Lumen](http://lumen.laravel.com)

[![Total Downloads](https://poser.pugx.org/acidjazz/larpug/downloads)](https://packagist.org/packages/acidjazz/larpug)
[![Latest Stable Version](https://poser.pugx.org/acidjazz/larpug/v/stable)](https://packagist.org/packages/acidjazz/larpug)
[![License](https://poser.pugx.org/acidjazz/larpug/license)](https://packagist.org/packages/acidjazz/larpug)
[![Build Status](https://travis-ci.org/acidjazz/larpug.svg?branch=master)](https://travis-ci.org/acidjazz/larpug)
[![Dependency Status](https://www.gemnasium.com/badges/github.com/acidjazz/larpug.svg)](https://www.gemnasium.com/github.com/acidjazz/larpug)
[![codecov](https://codecov.io/gh/acidjazz/larpug/branch/master/graph/badge.svg)](https://codecov.io/gh/acidjazz/larpug)
[![Codacy Badge](https://api.codacy.com/project/badge/Grade/26ae27120d1a4f248740b590a299f68e)](https://www.codacy.com/app/acidjazz/larpug?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=acidjazz/larpug&amp;utm_campaign=Badge_Grade)

[![Join the chat at https://gitter.im/acidjazz/larpug](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/acidjazz/larpug?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

# Requirements

* [NodeJS v6.x](https://nodejs.org/en/)
* [npm v3.x](https://www.npmjs.com/)


# Installation

Require this package with Composer

```bash
composer require acidjazz/larpug
```

Install the needed node modules to run pug
```bash
npm i --prefix vendor/acidjazz/larpug/node/
```

## Laravel

Once Composer has installed or updated your packages you need to register larpug with Laravel itself. Open up config/app.php and find the providers key, towards the end of the file, and add 'larpug\LarpugServiceProvider', to the end:

```php
'providers' => [
  ...
    larpug\LarpugServiceProvider::class,
],
```
## Lumen

For usage with [Lumen](http://lumen.laravel.com), add the service provider in `bootstrap/app.php`. 

```php
$app->register(larpug\LarpugServiceProvider::class);
```

# Usage

Using this is exactly the same way as using Blade templates, place your pug files in your `views` folder (usually in `resources/views`) and render them using `view()`

```php
namespace App\Controllers;

class Pages extends Controller
{
  public function index()
  {
    return view('pages.index', ['name' => 'kevin']);
  }

}
```

This will look for `resources/views/pages/index.pug` 

```pug
extends ../extends/layout

block content
  .page.index 
    .name=self.name
```
