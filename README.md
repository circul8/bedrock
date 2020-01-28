# Wordpress Stack
[![Packagist](https://img.shields.io/packagist/v/circul8/wordpress.svg?style=flat-square)](https://packagist.org/packages/circul8/wordpress)

Circul8's WordPress stack based on the [Root's Bedrock](https://github.com/roots/bedrock) with some pre-installed plugins.

---

## Installation

### 1. Init the project
Create a new project in a new folder:

It's important to set the ACF PRO key at the beginning otherwise the installation will fail:

  ```
    $ export ACF_PRO_KEY=123abc
    $ composer create-project circul8/wordpress your-project-folder-name
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


## Plugins

### Installing new plugins

Installing new plugins are usually disabled on production due to security reasons, therefore use composer:

1. Find the plugin at [WPackagist](https://wpackagist.org/)
1. Install the plugin `composer require wpackagist-plugin/akismet`

## Documentation / Reference

* [Bedrock](https://roots.io/bedrock/docs/)
* [Composer](https://getcomposer.org/)
* [WPackagist](https://wpackagist.org/)

## Change log
- v2.0.0 (2020-01-28)
  - Upgraded to latest Bedrock.
  - Removed starter theme -> ongoing projects should be headless.
  - Removed Timber plugin -> ongoing projects should be headless.
  - Upgraded to the Wordpress 5.3
  - All plugins updated.
- v1.0.0 (2019-03-14)
  - Versioning started. Wordpress upgraded to 5.1.1.
  - Fix of ACF to work with Guttenberg.
  - Upgraded to latest Bedrock.

---

# Local development

In order to develop this package locally, you need to switch to *develop* branch and run this command to test it:

`composer clearcache && composer create-project --repository-url={PATH}/project/packages.json circul8/wordpress`

Don't forget to change the *{PATH}* to the project repository. Also, look at the *packages.json* an change the `source.url`.

### Reference
 - https://gist.github.com/wimvds/7150868
