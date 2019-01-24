# cachet

This role installs and configures a Cachet status page.

## Requirements

Debian running a webserver like [nginx](https://github.com/stuvusIT/nginx) with [php](https://github.com/stuvusIT/php-fpm) and [MariaDB](https://github.com/stuvusIT/mariadb).

## Role Variables

`null` uses the Cachet default.

| Name                          | Default/Required   | Description                                                                |
|-------------------------------|:------------------:|----------------------------------------------------------------------------|
| `cachet_home`                 | `/srv/http/cachet` | Path to install Cachet to                                                  |
| `cachet_version`              | `v2.3.15`          | Cachet version to install                                                  |
| `cachet_worker_install`       | `true`             | Whether to install the Cachet worker (or queue runner) as a system service |
| `cachet_worker_delay`         | `2`                | Delay value for the worker                                                 |
| `cachet_worker_sleep`         | `1`                | Sleep value for the worker                                                 |
| `cachet_worker_trues`         | `3`                | Tries value for the worker                                                 |
| `cachet_url`                  | :heavy_check_mark: | Base URL for Cachet                                                        |
| `cachet_mysql_host`           | `localhost`        | MySQL host to connect to                                                   |
| `cachet_mysql_user`           | `cachet`           | MySQL database name to connect to                                          |
| `cachet_mysql_user`           | `cachet`           | MySQL user to connect with                                                 |
| `cachet_mysql_pass`           | `cachet`           | MySQL password to connect with                                             |
| `cachet_mysql_port`           | `null`             | MySQL port to use                                                          |
| `cachet_mysql_login_user`     | `root`             | Username for a MySQL user with permission to create users and databases    |
| `cachet_mysql_login_password` |                    | Password for the MySQL login user                                          |
| `cachet_mysql_db_prefix`      | `null`             | Prefix for database tables                                                 |
| `cachet_cache_driver`         | `apc`              | Cache driver to use                                                        |
| `cachet_session_driver`       | `apc`              | Session driver to use                                                      |
| `cachet_queue_driver`         | `database`         | Queue driver to use                                                        |
| `cachet_emoji`                | `true`             | Whether to enable emoji support                                            |
| `cachet_beacons`              | `false`            | Whether to automatically send beacons to Cachet                            |
| `cachet_mail_driver`          | `smtp`             | Mail driver to use                                                         |
| `cachet_mail_host`            | `mailtrap.io`      | Mail server to connect to                                                  |
| `cachet_mail_port`            | `2525`             | Port to connect to on the mail server                                      |
| `cachet_mail_username`        | `null`             | SMTP username to connect with                                              |
| `cachet_mail_password`        | `null`             | SMTP password to connect with                                              |
| `cachet_mail_address`         | `null`             | Mail address mails are sent from                                           |
| `cachet_mail_name`            | `null`             | Name mails are sent from                                                   |
| `cachet_mail_encryption`      | `tls`              | SMTP encryption to use                                                     |
| `cachet_redis_host`           | `null`             | Redis host to connect to                                                   |
| `cachet_redis_port `          | `null`             | Redis port to connect to                                                   |
| `cachet_redis_database`       | `null`             | Redis database to connect to                                               |
| `cachet_github_token`         | `null`             | Github token for Github authentication                                     |


## Example Playbook

```yml
- hosts: status
  roles:
  - cachet
     cachet_url: http://cachet.example.com
     cachet_mail_host: mymail.example.com
     cachet_mail_port: 25
     cachet_mail_username: cachet
     cachet_mail_password: ohCeiG4Oe3ueyo4suu8Z
     cachet_mail_address: cachet@example.com
     cachet_mail_name: Cachet
```

## License

This work is licensed under a [Creative Commons Attribution-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-sa/4.0/).

## Author Information

- [Janne Heß](https://github.com/dasJ)
