# RevolutPHPBundle 

## Installation

### Step 1: Download the Bundle

Open a command console, enter your project directory and execute the
following command to download the latest stable version of this bundle:

```console
$ composer require sverraest/revolut-php-bundle
```

This command requires you to have Composer installed globally, as explained
in the [installation chapter](https://getcomposer.org/doc/00-intro.md)
of the Composer documentation.

### Step 2: Enable the Bundle

Then, enable the bundle by adding it to the list of registered bundles
in the `app/AppKernel.php` file of your project:

```php
<?php
// app/AppKernel.php

// ...
class AppKernel extends Kernel
{
    public function registerBundles()
    {
        $bundles = array(
            // ...
            new Sverraest\RevolutPHPBundle\SverraestRevolutPHPBundle(),
        );

        // ...
    }

    // ...
}
```

### Step 3: Add configuration

You must specify the following configuration

```yaml
sverraest_revolut_php:
    api_key: 'foo'
    mode: 'production' # options are production or sandbox
```

### Step 4: Get the RevolutPHP Service or Autowire it

You can get an instance of the public RevolutPHP Service or autowire it.
```php
// src/AppBundle/Controller/AcmeController.php
...

$revolut = $this->get('revolut_php.client');
print_r($revolut->accounts->all())

...

```

Or via autowiring:

```php
// src/AppBundle/Service/AcmeService.php
...

public function __construct(RevolutPHP\Client $client) 
{
    $this->client = $client;
}

...
```

## Documentation

> Read the [documentation](Resources/doc/index.md) for this bundle
