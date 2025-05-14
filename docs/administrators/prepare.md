# Preparation of server for FusionResolveIT

This is the steps:

1. you must install database and PHP version + modules defined in the [requirements](./requirements.md).

1. uncompress the archive into a web folder

1. configure webserver 

    ## Nginx
    This is an example for nginx

    ```
    server {
        listen 80;

        root /var/www/fusionresolveit/public;
        index index.php;

        location /assets/ {
            alias /var/www/fusionresolveit/public/assets/;
        }

        location / {
            try_files \$uri /index.php\$is_args\$args;
        }

        location ~ \.php$ {
            try_files \$uri =404;
            fastcgi_split_path_info ^(.+\.php)(/.+)$;
            fastcgi_pass unix:/run/php/php8.2-fpm.sock;
            # fastcgi_pass 127.0.0.1:9000; # For port
            include fastcgi_params;
            fastcgi_param SCRIPT_FILENAME \$document_root\$fastcgi_script_name;
            fastcgi_param SCRIPT_NAME \$fastcgi_script_name;
            fastcgi_index index.php;
        }
    }
    ```

    ## Apache

    ```
    TODO
    ```

1.   ## Cli for verification

On cli, where is an argument to verify your server is ready (to use it you must be in the installation folder):

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

You are ready to install or upgrade, see next chapters !

