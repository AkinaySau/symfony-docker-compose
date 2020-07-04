FROM php:7.4-fpm

#COPY wait-for-it.sh /usr/bin/wait-for-it
#RUN chmod +x /usr/bin/wait-for-it
RUN apt-get update && apt-get install -y git wget zsh
RUN docker-php-ext-install pdo_mysql &&\
    git config --global user.email "akinaysau@gmail.com" &&\
    git config --global user.name "Vladimir Mogilev(Akinay Sau)"
#install symfony
RUN wget https://get.symfony.com/cli/installer -O - | bash
RUN mv /root/.symfony/bin/symfony /usr/local/bin/symfony
#install zsh
RUN sh -c "$(wget https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh -O -)"

COPY --from=composer /usr/bin/composer /usr/bin/composer
WORKDIR /var/www
CMD composer install ; bin/console doctrine:migrations:migrate ;  php-fpm
EXPOSE 9000
