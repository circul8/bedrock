# Wordpress Stack
[![Packagist](https://img.shields.io/packagist/v/circul8/wordpress.svg?style=flat-square)](https://packagist.org/packages/circul8/wordpress)

Circul8's WordPress stack based on the [Root's Bedrock](https://github.com/roots/bedrock) flavoured with [custom theme](https://github.com/circul8/wordpress-starter-theme) based on [Timber](http://timber.github.io/timber/).

---

## Installation

### 1. Init the project
Create a new project in a new folder:

It's important to set the ACF PRO key at the beginning otherwise the installation will fail:

  ```
    $ export ACF_PRO_KEY=123abc
    $ composer create-project circul8/wordpress:dev-master your-project-folder-name
  ```

### 2. Configure the DB

Update environment variables in `.env` file:

  * `DB_NAME` - Database name
  * `DB_USER` - Database user
  * `DB_PASSWORD` - Database password
  * `DB_HOST` - Database host
  * `WP_ENV` - Set to environment (`development`, `staging`, `production`)
  * `WP_HOME` - Full URL to WordPress home (http://example.com)
  * `WP_SITEURL` - Full URL to WordPress including subdirectory (http://example.com/wp)
  * `AUTH_KEY`, `SECURE_AUTH_KEY`, `LOGGED_IN_KEY`, `NONCE_KEY`, `AUTH_SALT`, `SECURE_AUTH_SALT`, `LOGGED_IN_SALT`, `NONCE_SALT`

### 3. Others

1. Set your site vhost document root to `/web` folder e.g. `/path/to/site/web/`

1. Access WP admin at `http://example.com/wp/wp-admin`

1. Activate the Starter Theme
   1. Set front page as a static page ![Screenshot](http://144.wtf/1Z2Jm+)
   1. Change desired page to Homepage template ![Screenshot](http://144.wtf/0EcIVx+)

1. Check the [Starter Theme](https://github.com/circul8/wordpress-starter-theme) documentation to see all installed plugins, filters, ...

## Plugins

### Installing new plugins

Installing new plugins are usually disabled on production due to security reasons, therefore use composer:

1. Find the plugin at [WPackagist](https://wpackagist.org/)
1. Install the plugin `composer require wpackagist-plugin/akismet`

### Must-Use Plugins

Check the [Starter Theme](https://github.com/circul8/wordpress-starter-theme#plugins) documentation.

## Documentation

* [Starter Theme](https://github.com/circul8/wordpress-starter-theme)
* [Bedrock](https://roots.io/bedrock/docs/)
* [Timber](http://timber.github.io/timber/)
* [Twig](https://twig.sensiolabs.org)
* [Composer](https://getcomposer.org/)
* [WPackagist](https://wpackagist.org/)
