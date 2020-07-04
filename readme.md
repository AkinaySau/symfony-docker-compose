# Readme
For open zsh: 
```bash
$ docker exec -it %_php-fpm_1 zsh
```
For install symfony: 
```bash
$ symfony new --full .
```

## Symfony
 - Project store `./src`

## Database
 - Data store `./db/data`
 - For import base data (only for first initialize a container) need
add `.sh`, `.sql` and `.sql.gz` in `./db/import` (if exist `./db/data`, then won't start this scripts)

[Read more](https://hub.docker.com/_/mariadb?tab=description)
