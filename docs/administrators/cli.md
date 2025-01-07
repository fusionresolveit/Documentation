# CLI usage

## How to use CLI

There are 2 methods to use the cli:

### First and preferred method

Run the command like an executable (preferred method):

```sh
./bin/cli
```

### Second method

In case first not works, prefix with *php* executable, something like (depend of the system):

```sh
php8.2 bin/cli
```


!!! info
    In this documentation, we use `./bin/cli`, if you use the second method, you must update the command before use it


## List commands

To list the commands available, run the cli without arguments or with --help

```sh
./bin/cli
```

and you will have something like this:

```
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
 FusionResolveIT cli, version 1.0.0

Commands:
*
  documentation    Give the link of the documentation
  migrate          Install / update FusionResolveIT
  prerequisites    Check all prerequisites are ok
  reset            Reset the database
  rollback         Rollback database migration

Run `<command> --help` for specific help
```

## Commands

Here are the commands.

### documentation

!!! info
    There is no argument for this command

!!! description
    This command will display the official web url for the documentation


The usage:
```sh
./bin/cli documentation
```
and you will have something like this:
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
This is the documentation link:

https://documentation.fusionresolveit.org

```

### prerequisites

!!! info
    There is no argument for this command

!!! description
    This command check the prerequisites for the app: version of PHP, PHP modules, database engine and database version

The usage:
```sh
./bin/cli documentation
```
and you will have something like this:
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
 PHP extension ctype .................................................. installed
 PHP extension curl ................................................... installed
 PHP extension fileinfo ............................................... installed
 PHP extension filter ................................................. installed
 PHP extension gd ..................................................... installed
 PHP extension iconv .................................................. installed
 PHP extension imap ................................................... installed
 PHP extension intl ................................................... installed
 PHP extension json ................................................... installed
 PHP extension mbstring ............................................... installed
 PHP extension pdo .................................................... installed
 PHP extension session ................................................ installed
 PHP extension simplexml .............................................. installed
 PHP extension sodium ................................................. installed
 PHP extension zlib ................................................... installed
 Database engine ....................................................... MariaDB
 Database version ......................................................... 10.5
```

In case something is wrong, you will have text in *red* and for some of them a comment line with more information.

### migrate

!!! info
    There is no argument for this command

!!! description
    This command install and update.

The usage:
```sh
./bin/cli migrate
```

You can run this command.
In case of the application is up to date, the command can be played and display

### reset

!!! danger
    **This command will delete all the data in the database**

!!! info
    There is no argument for this command

!!! description
    This command drop all tables in the database and reinstall the application into the database. **ALL DATA WILL BE DELETED**

If the command:

```sh
./bin/cli reset
```

is launched and the message appear `The database reset will not run because the database lock is present, check the documentation`, there is a security protection to prevent reset the database. You must rename or delete the file **database.lock** in the root folder, then run the command.


### rollback

!!! danger
    **This command will delete data in the database**

!!! info
    There is 2 arguments for this command:

    * --all / -a *rollback to the beginning (so delete all).* **It's the default argument**
    * --target number *the number is the number in the filename where you want to rollback in folder db/migrations*

If the command:

```sh
./bin/cli rollback --target 20241017094936
```

is launched and the message appear `The rollback will not run because the database lock is present, check the documentation`, there is a security protection to prevent rollback the database and so delete data. You must rename or delete the file **database.lock** in the root folder, then run the command.

!!! warning
    Be careful with this command, because with the rollback, it's possible (probably even) the application not works because tables in database missing.
