# Introduction

[![Latest Version](http://img.shields.io/packagist/v/astrotomic/laravel-translatable.svg?label=Release&style=for-the-badge)](https://packagist.org/packages/astrotomic/laravel-translatable)
[![MIT License](https://img.shields.io/github/license/Astrotomic/laravel-translatable.svg?label=License&color=blue&style=for-the-badge)](https://github.com/Astrotomic/laravel-translatable/blob/master/LICENSE)
[![Offset Earth](https://img.shields.io/badge/Treeware-%F0%9F%8C%B3-green?style=for-the-badge)](https://plant.treeware.earth/Astrotomic/laravel-translatable)
[![Larabelles](https://img.shields.io/badge/Larabelles-%F0%9F%A6%84-lightpink?style=for-the-badge)](https://www.larabelles.com/)

[![GitHub Workflow Status](https://img.shields.io/github/workflow/status/Astrotomic/laravel-translatable/run-tests?style=flat-square&logoColor=white&logo=github&label=Tests)](https://github.com/Astrotomic/laravel-translatable/actions?query=workflow%3Arun-tests)
[![StyleCI](https://styleci.io/repos/192333549/shield)](https://styleci.io/repos/192333549)
[![Codecov Coverage](https://img.shields.io/codecov/c/github/Astrotomic/laravel-translatable?logo=codecov&logoColor=white&label=Codecov&style=flat-square)](https://codecov.io/gh/Astrotomic/laravel-translatable)
[![Total Downloads](https://img.shields.io/packagist/dt/astrotomic/laravel-translatable.svg?label=Downloads&style=flat-square)](https://packagist.org/packages/astrotomic/laravel-translatable)
[![GitBook](https://img.shields.io/badge/GitBook-Astrotomic-7e57c2.svg?style=flat-square)](https://docs.astrotomic.info/laravel-translatable)

<p align="center">
    <img src="/art/socialcard.png" alt="laravel-translatable socialcard">
</p>

**If you want to store translations of your models into the database, this package is for you.**

This is a Laravel package for translatable models. Its goal is to remove the complexity in retrieving and storing multilingual model instances. With this package you write less code, as the translations are being fetched/saved when you fetch/save your instance.

The full documentation can be found at [GitBook](https://docs.astrotomic.info/laravel-translatable).

## Installation

```bash
composer require mohsen-tq/laravel-translatable
```

## Quick Example

### **Getting translated attributes**

```php
$post = Post::first();
echo $post->translate('en')->title; // My first post

App::setLocale('en');
echo $post->title; // My first post

App::setLocale('de');
echo $post->title; // Mein erster Post
```

### **Get Model with translate selected data**
```php
$post->WithTranslation(['title','descriptin'])

```
### **Saving translated attributes**

```php
$post = Post::first();
echo $post->translate('en')->title; // My first post

$post->translate('en')->title = 'My cool post';
$post->save();

$post = Post::first();
echo $post->translate('en')->title; // My cool post
```

### **Filling multiple translations**

```php
$data = [
  'author' => 'Gummibeer',
  'en' => ['title' => 'My first post'],
  'fr' => ['title' => 'Mon premier post'],
];
$post = Post::create($data);

echo $post->translate('fr')->title; // Mon premier post
```

### Security

If you discover any security related issues, please check [SECURITY](https://github.com/MohsenTQ/.github/blob/master/SECURITY.md) for steps to report it.



## Versions

| Package           | Laravel                       | PHP       |
| :---------------- | :---------------------------- | :-------- |
| **v11.6 - v11.9** | `5.8.* / 6.* / 7.* / 8.*`     | `>=7.2`   |
| **v11.4 - v11.5** | `5.6.* / 5.7.* / 5.8.* / 6.*` | `>=7.1.3` |
| **v11.0 - v11.3** | `5.6.* / 5.7.* / 5.8.*`       | `>=7.1.3` |


