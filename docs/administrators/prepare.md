# Preparation of server for FusionResolveIT

This is the steps:

1. you must install database and PHP version + modules defined in the [requirements](./requirements.md).

1. uncompress the archive into a web folder

1. configure webserver 
    * for NGINX:
        ```
        location /fusionresolveit/assets/ {
            alias /...tofill.../fusionresolveit/assets/;
        }
        location /fusionresolveit/ {
            include fastcgi_params;
            fastcgi_split_path_info ^/fusionresolveit(.*)(/.*)$;
            fastcgi_pass 127.0.0.1:9000; # For port
            # fastcgi_pass unix:/run/php/php8.2-fpm.sock; # for socket
            factcgi_param   HTTP_REFERER $http_referer;
            factcgi_param   SCRIPT_FILENAME /...tofill.../fusionresolveit/public/index.php$fascgi_script_name;
            factcgi_param   SERVER_NAME $host;
        }
        ```

    * for Apache:
        ```
        TODO
        ```

You are ready to install or upgrade, see next chapters !

