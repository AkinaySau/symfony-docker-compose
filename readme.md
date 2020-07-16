# Readme
## Install
To start, copy `.env.example ' to`. env` and change your ports (if necessary)

Open zsh: 
```bash
$ docker exec -it %_php-fpm_1 zsh
```
For install symfony: 
```bash
$ symfony new --full .
```

## Symfony
 - Project store `./src`
### Webpack encore
For use encore run command in symfony container


For enable hot reload 
```js
// webpack.config.js
...
Encore
  // any configs

  //add configs for dev server 
  .configureDevServerOptions(options => {
    options.port = 80, 
    options.host = '0.0.0.0',
    options.watchOptions = {
      aggregateTimeout: 500,
      poll: 1000,
        };
  })
```
## Database
 - Data store `./db/data`
 - For import base data (only for first initialize a container) need
add `.sh`, `.sql` and `.sql.gz` in `./db/import` (if exist `./db/data`, then won't start this scripts)

[Read more](https://hub.docker.com/_/mariadb?tab=description)
