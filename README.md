![](https://bosnadev.com/wp-content/uploads/2015/01/laravel_envoy.png)
## Installation
`composer require sikic/laravel-envoy`

## Configuration
`php artisan vendor:publish --provider="Luka\Envoy\EnvoyServiceProvider"`


## Usage 
This is just an example, in production, you probably want to put this in queue
```
<?php

namespace App\Http\Controllers;

use Luka\Envoy\Facades\Worker;

class HomeController extends Controller
{
    public function index()
    {
        return Worker::task('echo')->arguments([
            'text' => 'hello world!'
        ])->run();
    }
}

```
