laravel-admin Media player
======

This extension allows you to play video or audio on grid pages and show pages with the help of [mediaelement](https://github.com/mediaelement/mediaelement).

## Screenshots

![wx20181114-010912](https://user-images.githubusercontent.com/1479100/48430450-4ef5fa80-e7aa-11e8-8fcd-1f5717b0d3d6.png)

![wx20181114-011037](https://user-images.githubusercontent.com/1479100/48430451-4ef5fa80-e7aa-11e8-8394-38ed2c6c75ba.png)


## Installation

```bash
composer require laravel-admin-ext/media-player

php artisan vendor:publish --tag=laravel-admin-media-player
```

## Usage

如果你有一个字段`foo`存储的是音频/视频文件的完整url，或者是在`admin.upload.disk`所配置的disk下的路径，可以通过下面的方式使用

在列表中：
```php
// 给当前字段列增加一个播放按钮，点击之后会打开一个modal，可播放视频文件
$grid->foo()->video();

// 给当前字段列增加一个音频播放器
$grid->foo()->audio();
```
在详情页：
```php
// 这个字段将会显示成为一个视频播放器
$show->foo()->video();

// 这个字段将会显示成为一个音频播放器
$show->foo()->audio();
```

如果字段`foo`是其它路径或者其它服务器下的文件路径，可以使用如下设置

```php
$grid->foo()->video(['server' => 'http:www.foo.com/']);
```

这个扩展的播放器功能是基于[mediaelement](https://github.com/mediaelement/mediaelement)，可以参考[API and Configuration](https://github.com/mediaelement/mediaelement/blob/master/docs/api.md)给播放器增加更多的设置。

比如设置播放器的尺寸：

```php
$grid->foo()->video(['videoWidth' => 720, 'videoHeight' => 480]);
```


## Donate

如果觉得这个项目帮你节约了时间，不妨支持一下;)

![-1](https://cloud.githubusercontent.com/assets/1479100/23287423/45c68202-fa78-11e6-8125-3e365101a313.jpg)

License
------------
Licensed under [The MIT License (MIT)](LICENSE).





