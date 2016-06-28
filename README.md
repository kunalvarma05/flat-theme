Flat
====

Flat is a sleek, clean and elegant theme for [SAMI](https://github.com/FriendsOfPHP/Sami). I wasn't really fond of the default theme provided by SAMI, so I hacked up a simple child theme.

Usage
=====

```php
<?php

use Sami\Sami;
use Symfony\Component\Finder\Finder;

$iterator = Finder::create()
->files()
->name('*.php')
->exclude('Resources')
->exclude('Tests')
->in('/path/to/src');

$config = array(
    'theme'                => "flat",
    'title'                => 'My API',
    'build_dir'            => __DIR__."/%version%",
    'cache_dir'            => __DIR__."/cache/%version%",
    'default_opened_level' => 2,
    );

$sami = new Sami($iterator, $config);

//Add the theme's parent directory
//to SAMI, so that the theme can
//be resolved while rendering.

$templates = $sami['template_dirs'];
$templates[] = __DIR__ . '/themes/';
$sami['template_dirs'] = $templates;

return $sami;
?>
```

Screenshots
===========
### Class
![flat-theme-main](https://cloud.githubusercontent.com/assets/893057/16435162/91b910aa-3db1-11e6-9a1c-575a336ad767.png)

### Classes
![flat-theme-classes](https://cloud.githubusercontent.com/assets/893057/16435164/91cc13d0-3db1-11e6-9433-cfac5000e621.png)

### Methods
![flat-theme-methods](https://cloud.githubusercontent.com/assets/893057/16435165/91cf142c-3db1-11e6-96d1-51e5ecf75dce.png)

### Details
![flat-theme-details](https://cloud.githubusercontent.com/assets/893057/16435161/918ed5c4-3db1-11e6-8790-e97372491fa0.png)

### Search
![flat-theme-search](https://cloud.githubusercontent.com/assets/893057/16435163/91ca1152-3db1-11e6-8b20-f4d702c8bed9.png)

## License
Flat is licensed under The MIT License (MIT).