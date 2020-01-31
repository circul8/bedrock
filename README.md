# Wordpress Stack
[![Packagist](https://img.shields.io/packagist/v/circul8/wordpress.svg?style=flat-square)](https://packagist.org/packages/circul8/wordpress)

> Circul8's WordPress stack based on the [Root's Bedrock](https://github.com/roots/bedrock) with some pre-installed plugins.

## Installation

### 1. Init the project
Create a new project in a new folder:

It's important to set the ACF PRO key at the beginning otherwise the installation will fail:

  ```sh
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

### Pre-installed plugins

1. [Classic Editor](https://wordpress.org/plugins/classic-editor/) (activated -> MU* plugin)
   - We don't use the Gutenberg.
1. [Disable Comments](https://wordpress.org/plugins/disable-comments/) (activated -> MU* plugin)
   - All comments must be disabled. We don't use this functionallity. Also, it's a security hole.
1. [Duplicate Post](https://wordpress.org/plugins/duplicate-post) (activated -> MU* plugin)
   - Administration UX tweak to easily copy/paste posts.
1. [Post Types Order](https://wordpress.org/plugins/post-types-order) (activated -> MU* plugin)
   - Administration UX tweak to easily reorder posts.
1. [Tinymce Advanced](https://wordpress.org/plugins/tinymce-advanced) (activated -> MU* plugin)
   - WYSIWYG enahancement.
1. [Advanced Custom Fields PRO](https://wordpress.org/plugins/advanced-custom-fields-pro) (activated -> must use)
   - Most important plugin.
1. [Wordfence](https://wordpress.org/plugins/wordfence) (not activated)
   - This is not mandatory plugin, but recommended. Security.
1. [WP Mail SMTP](https://wordpress.org/plugins/wp-mail-smtp) (not activated)
   - This is not mandatory plugin, but recommended, `wpmail()` is not reliable. Company policy is to use Mailgun.

**MU - Must Use Plugin*

### Installing new plugins

Installing new plugins are usually disabled on production due to security reasons, therefore use composer:

1. Find the plugin at [WPackagist](https://wpackagist.org/)
1. Install the plugin `composer require wpackagist-plugin/akismet`

## Testing & Coding style

The PHPCS has been removed due to the fact this is just a scaffold for WP Headless projects that should use WP plugins only without any theme.

If additional functionality is needed, follow the [Circul8 Coding Standards here](https://github.com/circul8/coding-standards).

## Local development

In order to develop this project package locally, you need to:
1. Clone this repo
1. Do your changes in the clone
1. Commit changes (do not push)
1. Create `packages.json` somewhere (see bellow)
1. Run the `create-project` with specified `packages.json` (see bellow)

### `create-project`

```bash
$ composer clearcache && export ACF_PRO_KEY="123==" && composer create-project --repository-url={YOURPATH}/packages.json circul8/wordpress:dev-master
```

Don't forget to change the *{YOURPATH}* to your `packages.json`.

### `packages.json`

```json
{
  "package": {
      "name": "circul8/wordpress",
      "version": "1.0.0",
      "source": {
        "url": "{YOURPATH}wordpress/.git",
        "type": "git",
        "reference": "{YOURBRANCH}"
      }
  }
}
```

Again, don't forget to change the *{YOURPATH}*. This time it must lead to the cloned repository of the `circul8/wordpress`. You also need to change the *{YOURBRANCH}* to your testing branch.

#### Reference
 - https://gist.github.com/wimvds/7150868

## Documentation / Reference

* [Bedrock](https://roots.io/bedrock/docs/)
* [Composer](https://getcomposer.org/)
* [WPackagist](https://wpackagist.org/)


---

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
