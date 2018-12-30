# B2-Backblaze Storage Adapter for Laravel 5

[![Latest Version on Packagist](https://img.shields.io/packagist/v/bringyourownideas/laravel-backblaze.svg?style=flat-square)](https://packagist.org/packages/bringyourownideas/laravel-backblaze)
[![Total Downloads](https://img.shields.io/packagist/dt/bringyourownideas/laravel-backblaze.svg?style=flat-square)](https://packagist.org/packages/bringyourownideas/laravel-backblaze)

Backblaze B2 is a cloud storage system comparable to Amazons S3. This adapter allows you to use B2 within Laravel 5 applications.

At [bring your own ideas Ltd.](https://bringyourownideas.com) it is used in combination with [spatie's Laravel backup](https://github.com/spatie/laravel-backup) to backup our Laravel projects.

The code is based on [Paul Olthof](https://github.com/hpolthof)s [unmaintained repo](https://github.com/hpolthof/laravel-backblaze) and addresses mostly bugs at this point.

## Installation

Via Composer
```
composer require bringyourownideas/laravel-backblaze
```

In your app.php config file add to the list of service providers:
```
\bringyourownideas\Backblaze\BackblazeServiceProvider::class,
```

Add the following to your filesystems.php config file in the ```disks``` section:
```
'b2' => [
    'driver'         => 'b2',
    'accountId'      => '',
    'applicationKey' => '',
    'bucketName'     => '',
],
```

Now just paste in your credentials and bucketname and you're ready to go!

## Usage
Just use it as you normally would use the Storage facade.
```
\Storage::disk('b2')->put('test.txt', 'test')
```
and
```
\Storage::disk('b2')->get('test.txt')
```

## Credits

* [Paul Olthof](https://github.com/hpolthof)
* [Ramesh Mhetre](https://github.com/mhetreramesh/flysystem-backblaze)
* [Chris White](https://github.com/cwhite92/b2-sdk-php)

## License

MIT, as the original repository.