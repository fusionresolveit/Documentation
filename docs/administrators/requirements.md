# Requirements

* a webserver (e.g. Nginx, Apache)
* PHP 8.2 or 8.3
* PHP extensions:
    * ctype
    * curl
    * fileinfo
    * gd
    * iconv
    * imap
    * intl
    * json
    * mbstring
    * mysqli
    * PDO\_MYSQL (if you use MariaDB)
    * PDO\_PGSQL (if you use PostgreSQL)
    * simplexml
    * zlib
* one of the following database:

  | Database       | Supported versions         |
  |----------------|----------------------------|
  | MariaDB        | 10.5 / 10.6 / 10.11 / 11.4 |
  | PostgreSQL     | 13 / 14 / 15 / 16 / 17     |

!!! warning
    MySQL is forbidden due to cache problem with some type of queries.
    