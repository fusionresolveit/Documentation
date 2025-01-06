# Requirements

## Description

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

## Cli for verification

On cli, where is an argument to verify your server is ready:

```sh
./bin/cli prerequisites
```

You will have something like this:

```sh
 ================================================================================
     ______           _             ____                  __           __________
    / ____/_  _______(_)___  ____  / __ \___  _________  / /   _____  /  _/_  __/
   / /_  / / / / ___/ / __ \/ __ \/ /_/ / _ \/ ___/ __ \/ / | / / _ \ / /  / /
  / __/ / /_/ (__  ) / /_/ / / / / _, _/  __(__  ) /_/ / /| |/ /  __// /  / /
 /_/    \__,_/____/_/\____/_/ /_/_/ |_|\___/____/\____/_/ |___/\___/___/ /_/


  FusionResolveIT cli tool

 ================================================================================

 Environment:
 PHP Version ............................................................ 8.2.26                                                                                                                          
 FusionResolveIT Version ................................................. 1.0.0                                                                                                                          

 ================================================================================
This is the prerequisites:

 Prerequisites:
 PHP Version ............................................................ 8.2.26                                                                                                                          
 PHP extensionctype .................................................. installed                                                                                                                          
 PHP extensioncurl ................................................... installed                                                                                                                          
 PHP extensionfileinfo ............................................... installed                                                                                                                          
 PHP extensionfilter ................................................. installed                                                                                                                          
 PHP extensiongd ..................................................... installed                                                                                                                          
 PHP extensioniconv .................................................. installed                                                                                                                          
 PHP extensionimap ................................................... installed                                                                                                                          
 PHP extensionintl ................................................... installed                                                                                                                          
 PHP extensionjson ................................................... installed                                                                                                                          
 PHP extensionmbstring ............................................... installed                                                                                                                          
 PHP extensionpdo .................................................... installed                                                                                                                          
 PHP extensionsession ................................................ installed                                                                                                                          
 PHP extensionsimplexml .............................................. installed                                                                                                                          
 PHP extensionsodium ................................................. installed                                                                                                                          
 PHP extensionzlib ................................................... installed                                                                                                                          
 Database engine ....................................................... MariaDB                                                                                                                          
 Database version ......................................................... 10.5
```