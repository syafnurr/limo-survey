
## NOTE
We are using **LimeSurvey CE (Community Edition)**. The source code was a zip file, so unfortunately there's no `composer.json` and `package.json` files - which means we have to commit the entire dependencies (in `vendor/` and `node_modules/`).

## Version
### LimeSurvey CE 6.6.1

## Installation
Please refer to the [installation manual](https://manual.limesurvey.org/Installation_-_LimeSurvey_CE) for installation guides.\
Particularly:
- A webserver (Apache or Nginx)
- PHP `^7.4` or `8.*`
- `mysql >= 5.5.9` | `pgsql >= 9` | `mariadb >= 5.5`
- php.ini configurations:
  - `short_open_tag` = `On`
  - Extensions:
    - `mbstring`
    - `hash`
    - `session`
    - `openssl`
    - `fileinfo`
    - `gd2`
    - `imap`
    - `ldap`
    - `zip`
    - `zlib`
    - `pdo_mysqli`
    - `pdo_pgsql`

Place the LimeSurvey directory inside the webserver's serving directory (e.g `/var/www/html`).

Directory permissions:\
For the script to work properly it needs certain access to some directories - this applies especially to Linux/*nix systems.
- The `/limesurvey/tmp` directory **(and all its subdirectories and files)** are used for imports & uploads and should be set to `Read & Write` for your webserver.
- The `/limesurvey/upload/` directory **(and all its subdirectories and files)** must also have `Read & Write` for your webserver in order to enable picture and media files upload.
- The `/limesurvey/application/config/` directory also needs `Read & Write` permissions for your webserver.
- The `other` directories can be set to `Read Only`. You may wish in Linux/Unix to set the permissions on each file within the `/limesurvey/admin` directory to `Read Only`.


## Configuration
* `config.php`
   * Copy `application/config/config.example.php` into `application/config/config.php`
   * Edit the section `components->db` to your correct db connection settings, namely the `connectionString`, `user`, `password`
* To enable debugging, check the section `config`: 
   * `debug` for application errors
   * `debugsql` to show all queries for every request (appears at the bottom of the page).

<br>

---

<br>

<br>

---

<br>

<img src="https://www.limesurvey.org/images/limesurvey/svg/logo_limesurvey_head.svg" width="600" alt='LimeSurvey Logo' />

# Sophisticated online survey software
![Build status](https://github.com/LimeSurvey/LimeSurvey/actions/workflows/main.yml/badge.svg)


## About
Limesurvey is the number one open-source survey software.

Advanced features like branching and multiple question types make it a valuable partner for survey-creation.

### Demo

See our [Administration Demo](http://demo.limesurvey.org/index.php?r=admin/authentication/sa/login).
The credentials are prefilled, just click **Log in**

Or try taking one of our [test surveys](https://survey.limesurvey.org/index.php?sid=78184&lang=en)


## How to install

### Release
We release early and often.
The latest stable release version is available for download at https://community.limesurvey.org/downloads/
We recommend using those.

### Repository
You may want to use the plain repository, which is also possible.

Please be advised, that we sometimes push development versions into the repository, which may not be working correctly.

## Requirements

### Minimal
The absolute minimal requirements are:
 - Apache >= 2.4 | nginx >= 1.1 | any other php-ready webserver
 - php >= 7.4
    - with mbstring and pdo-database drivers
 - mysql >= 5.5.9 | pgsql >= 9 | mariadb >= 5.5  | mssql >= 2005

### Recommended
We recommend the following setup
 - Web server: nginx (most recent stable version)
 - PHP (most recent stable version)
    - with php-fpm, mbstring, gd2 with freetype, imap, ldap, zip, zlib and database drivers
 - MariaDB or MySQL (most recent stable version)

## Manual
for more information please refer to our [homepage](http://www.limesurvey.org), or have a look at the [manual](http://manual.limesurvey.org) 

## License
LimeSurvey software is licensed under the [GPL 2.0](https://www.gnu.org/licenses/old-licenses/gpl-2.0.en.html), or at your choice any later version of the license.

Pictures and the LimeSurvey Logo are registered trademarks of LimeSurvey GmbH, Hamburg, Germany.

## Tools used
We are using BrowserStack to run manual tests on different browsers and devices

[![](https://raw.githubusercontent.com/LimeSurvey/LimeSurvey/master/docs/contributions/browserstack-logo.png "Checkout BrowserStack")](https://www.browserstack.com/)

We are using Github Actions to run automated tests before release.

![Main workflow](https://github.com/LimeSurvey/LimeSurvey/actions/workflows/main.yml/badge.svg)
