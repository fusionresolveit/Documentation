# Update / upgrade

## Requirements

First step, must verify [requirements](./requirements.md) are ok.


## Update from GSIT 9.5 or GLPI 9.5.x

!!! tip "Tip: from MariaDB to PostgreSQL"
    With the migration from GSIT or GLPI to FusionResolveIT, you are able to migrate from MariaDB to PostgreSQL, but **you must choice now** because will be not possible after.

To do this, you must fill the file at the root of the folder, named `phinx.php`.

The key `default_environment` define the name of your new database, **must be created with no tables inside**.

### MariaDB

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

### PostgreSQL

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

### Define old database with the data

Now, you need to configure access to the old database.
FusionResolveIT will not write on it, so to prevent problem, you can define a username with only read right.

Uncomment into `phinx.php` file the part named `old`, like:


```
    'old' => [
      'adapter' => 'mysql',              // NOT TOUCH THIS
      'host' => 'localhost',             // the database hostname
      'name' => 'glpi',                  // the database name
      'user' => 'glpi',                  // the username
      'pass' => 'mypass',                // the username password
      'port' => '3306',                  // port of the database
      'charset' => 'utf8mb4',            // NOT TOUCH THIS
      'collation' => 'utf8_unicode_ci',  // NOT TOUCH THIS
    ],
```

You are ready for the migration!


## Update from GLPI 10.0.x

The upgrade is not yet tested with this version, but the migration is the same than previous part.

## Run the migration

Now, you need to run the migration.

Run this command (command line only) :

```sh
./bin/cli migrate
```

!!! info
    The migration can take couple minutes to 2 - 3 hours for huge database


In case of errors, please create an issue [here](https://github.com/fusionresolveit/issues/issues) with the error and the type and version of database used.




