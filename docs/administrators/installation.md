# Installation

This chapter is used if you install from scratch.

!!! note
    If you update from version 9.5.x of **GSIT** or upgrade from **GLPI**, please refer to [update / upgrade chapter](./update.md).


You can install with Database MariaDB or PostgreSQL.

To do this, you must fill the file at the root of the folder, named `phinx.php`.


## MariaDB

By default, it use the database with key `production` for MariaDB database.

You must define your database information into the part named `production`, like:

```
    'production' => [
      'adapter' => 'mysql',                 // NOT TOUCH THIS
      'host' => 'localhost',                // the database hostname
      'name' => 'fusionresolveit',          // the database name
      'user' => 'fusionresolveit',          // the username
      'pass' => 'mypass',                   // the username password
      'port' => '3306',                     // port of the database
      'charset' => 'utf8mb4',               // NOT TOUCH THIS
      'collation' => 'utf8mb4_general_ci',  // NOT TOUCH THIS
    ],
```

## PostgreSQL

If you want to use the PotgreSQL database, change the `default_environment` value by `productionpgsql` and update database information in part with the same name, like:

```
    'productionpgsql' => [
      'adapter' => 'pgsql',              // NOT TOUCH THIS
      'host' => 'localhost',             // the database hostname
      'name' => 'fusionresolveit',       // the database name
      'user' => 'fusionresolveit',       // the username
      'pass' => 'mypass',                // the username password
      'port' => '5432',                  // port of the database
      'charset' => 'utf8',               // NOT TOUCH THIS
      'collation' => 'utf8_general_ci',  // NOT TOUCH THIS
    ],
```


## Run the migration

Now, you need to run the migration to install the database.

Run this command (in command line only) :

```sh
./bin/cli migrate
```

In case of errors, please create an issue [here](https://github.com/fusionresolveit/issues/issues) with the error and the type and version of database used.


## Default username

The default username / password to connect to FusionResolveIT is : 

*admin* / *AdminIT*
