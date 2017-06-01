# [Wordpress Stack]
[![Packagist](https://img.shields.io/packagist/v/circul8/wordpress.svg?style=flat-square)](https://packagist.org/packages/circul8/wordpress)

Circul8's WP stack based on the [Root's Bedrock](https://github.com/roots/bedrock) flavoured with [custom theme](https://github.com/circul8/wordpress-starter-theme) based on [Timber](http://timber.github.io/timber/).

## Installation

1. Create a new project in a new folder for your project:

  `composer create-project circul8/wordpress:dev-master your-project-folder-name`

1. Update environment variables in `.env`  file:
  * `DB_NAME` - Database name
  * `DB_USER` - Database user
  * `DB_PASSWORD` - Database password
  * `DB_HOST` - Database host
  * `WP_ENV` - Set to environment (`development`, `staging`, `production`)
  * `WP_HOME` - Full URL to WordPress home (http://example.com)
  * `WP_SITEURL` - Full URL to WordPress including subdirectory (http://example.com/wp)
  * `AUTH_KEY`, `SECURE_AUTH_KEY`, `LOGGED_IN_KEY`, `NONCE_KEY`, `AUTH_SALT`, `SECURE_AUTH_SALT`, `LOGGED_IN_SALT`, `NONCE_SALT`

1. Set your site vhost document root to `/path/to/site/web/` (`/path/to/site/current/web/` if using deploys)

1. Access WP admin at `http://example.com/wp/wp-admin`

1. Activate the Starter Theme

1. Set front page as a static page

	![Screenshot](http://144.wtf/1Z2Jm+)

1. Change desired page to Homepage template

	![Screenshot](http://144.wtf/0EcIVx+)

1. Check the [Starter Theme](https://github.com/circul8/wordpress-starter-theme) documentation to see all installed plugins, filters, ...

## Documentation

* [Starter Theme](https://github.com/circul8/wordpress-starter-theme)
* [Bedrock](https://roots.io/bedrock/docs/)
* [Timber](http://timber.github.io/timber/)
