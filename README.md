# League\Flysystem

[![Author](http://img.shields.io/badge/author-@frankdejonge-blue.svg?style=flat-square)](https://twitter.com/frankdejonge)
[![Build Status](https://img.shields.io/travis/thephpleague/flysystem/master.svg?style=flat-square)](https://travis-ci.org/thephpleague/flysystem)
[![Coverage Status](https://img.shields.io/scrutinizer/coverage/g/thephpleague/flysystem.svg?style=flat-square)](https://scrutinizer-ci.com/g/thephpleague/flysystem/code-structure)
[![Quality Score](https://img.shields.io/scrutinizer/g/thephpleague/flysystem.svg?style=flat-square)](https://scrutinizer-ci.com/g/thephpleague/flysystem)
[![Software License](https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square)](LICENSE)
[![Packagist Version](https://img.shields.io/packagist/v/league/flysystem.svg?style=flat-square)](https://packagist.org/packages/league/flysystem)
[![Total Downloads](https://img.shields.io/packagist/dt/league/flysystem.svg?style=flat-square)](https://packagist.org/packages/league/flysystem)

[![SensioLabsInsight](https://insight.sensiolabs.com/projects/9820f1af-2fd0-4ab6-b42a-03e0c821e0af/big.png)](https://insight.sensiolabs.com/projects/9820f1af-2fd0-4ab6-b42a-03e0c821e0af)

Flysystem is a filesystem abstraction which allows you to easily swap out a local filesystem for a remote one.

# Goals

* Have a generic API for handling common tasks across multiple file storage engines.
* Have consistent output which you can rely on.
* Integrate well with other packages/frameworks.
* Be cacheable.
* Emulate directories in systems that support none, like AwsS3.
* Support third party plugins.
* Make it easy to test your filesystem interactions.
* Support streams for big file handling.

# Installation

Through Composer, obviously:

```
composer require league/flysystem
```

You can also use Flysystem without using Composer by registering an autoloader function:

```php
spl_autoload_register(function($class) {
    $prefix = 'League\\Flysystem\\';

    if ( ! substr($class, 0, 17) === $prefix) {
        return;
    }

    $class = substr($class, strlen($prefix));
    $location = __DIR__ . 'path/to/flysystem/src/' . str_replace('\\', '/', $class) . '.php';

    if (is_file($location)) {
        require_once($location);
    }
});
```

## Integrations

Want to get started quickly? Check out some of these integrations:

* Laravel integration: https://github.com/GrahamCampbell/Laravel-Flysystem
* Symfony integration: https://github.com/1up-lab/OneupFlysystemBundle
* Zend Framework integration: https://github.com/bushbaby/BsbFlysystem
* CakePHP integration: https://github.com/WyriHaximus/FlyPie
* Silex integration: https://github.com/WyriHaximus/SliFly
* Cilex integration: https://github.com/WyriHaximus/cli-fly
* Yii 2 integration: https://github.com/creocoder/yii2-flysystem
* Backup manager: https://github.com/heybigname/backup-manager
* Drupal: https://www.drupal.org/project/flysystem

## Adapters

* Local
* Amazon Web Services - S3 V2: https://github.com/thephpleague/flysystem-aws-s3-v2
* Amazon Web Services - S3 V3: https://github.com/thephpleague/flysystem-aws-s3-v3
* Rackspace Cloud Files: https://github.com/thephpleague/flysystem-rackspace
* Dropbox: https://github.com/thephpleague/flysystem-dropbox
* OneDrive: https://github.com/jacekbarecki/flysystem-onedrive
* Copy: https://github.com/thephpleague/flysystem-copy
* Ftp
* Sftp (through phpseclib): https://github.com/thephpleague/flysystem-sftp
* Zip (through ZipArchive): https://github.com/thephpleague/flysystem-ziparchive
* WebDAV (through SabreDAV): https://github.com/thephpleague/flysystem-webdav
* PHPCR: https://github.com/thephpleague/flysystem-phpcr
* Azure Blob Storage
* NullAdapter
* Redis (through Predis): https://github.com/danhunsaker/flysystem-redis
* Fallback: https://github.com/Litipk/flysystem-fallback-adapter
* Memory: https://github.com/thephpleague/flysystem-memory
* Google Cloud Storage: https://github.com/Superbalist/flysystem-google-storage
* SinaAppEngine Storage: https://github.com/litp/flysystem-sae-storage
* Gaufrette: https://github.com/jenkoian/flysystem-gaufrette

## Caching

* Memory (array caching)
* Redis (through Predis)
* Memcached
* Adapter
* Stash

## Documentation

[Check out the documentation](http://flysystem.thephpleague.com/)

## Security

If you discover any security related issues, please email frenky@frenky.net instead of using the issue tracker.


# Enjoy

Oh and if you've come down this far, you might as well follow me on [twitter](http://twitter.com/frankdejonge).
