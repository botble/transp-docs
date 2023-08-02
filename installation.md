# Introduction

## Requirement

- Apache, nginx, or another compatible web server.
- PHP >= 8.0
- MySQL Database server
- BCMath PHP Extension
- Ctype PHP Extension
- Fileinfo PHP extension
- JSON PHP Extension
- Mbstring PHP Extension
- OpenSSL PHP Extension
- PDO PHP Extension
- Tokenizer PHP Extension
- XML PHP Extension
- Module Re_write server
- PHP_CURL Module Enable

## PHP Configuration

Open your php configuration file php.ini and change the following settings.

```ini
memory_limit = 128M
max_execution_time = 600
```

If you are using Cpanel, you can follow [this article](https://chemicloud.com/kb/article/how-to-increase-the-php-memory-limit-in-cpanel/) to change your PHP memory limit settings.

::: warning
On this project, we're using the latest Laravel version (currently 8.x). Please go to [Laravel documentation page](https://laravel.com/docs) for more information.

It’s based on Laravel framework, the root folder for it is /public. You shouldn’t install it on a sub-folder, use sub-domain is better than sub-folder. (we won’t support to install our product on sub-folder).
:::

## Video tutorial install via GUI

<iframe width="100%" height="360" src="" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Install via GUI

- Create database and extract source codes into your web root directory.
- Go to `[your-domain.com]` to start installation.
- Step by step to setup your database conntection, site information and administrator.
- Login and setup your website on **Welcome Board**.

## Install on hosting (manual)

::: warning
If you're a Laravel developer and you want to customize our source code in `platform/core` and `platform/packages`, you need to delete folder `/vendor` then run command `composer install` to reinstall vendor packages.
:::

- Upload all files into the root folder of your hosting (normally, it is`public_html`).
- Create a database and import data from `database.sql` (it's located in source code).
  ![Database](/images/directory-and-database.png)
- Update your database credentials and `APP_URL` in `.env`
  ![Env](/images/env-example.png)
- Go to `/admin` to access to admin panel.
- The default admin account is `admin` - `12345678`.
  ![Login](/images/admin-page.png)

## Install locally or in VPS (manual)

::: warning
If you're a Laravel developer and you want to customize our source code in `platform/core` and `platform/packages`, you need to delete folder `/vendor` then run command `composer install` to reinstall vendor packages.
:::

- Update your database credentials and `APP_URL` in `.env`
  ![Env](/images/env-example.png)

- Using sample data:
    - Import database from `database.sql`.

- Don't use sample data:
    - Run `php artisan migrate` to create database structure.

    - Run `php artisan cms:user:create` to create admin user.

    - Run `php artisan cms:theme:activate iori`

- If you're pulled source code from GIT server:
    - Run `php artisan vendor:publish --tag=cms-public --force`

- Run web locally:
    - Change `APP_URL` in `.env` to `APP_URL=http://localhost:8000`
    - Run `php artisan serve`. Open `http://localhost:8000`, you should see the homepage.
    - Go to `/admin` to access to admin panel.
    - If you're using sample data, the default admin account is `admin` - `12345678`.
    - If you don't use sample data, you need to go to Admin -> Plugins then activate all plugins.
