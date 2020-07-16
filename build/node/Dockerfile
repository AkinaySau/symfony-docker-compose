FROM node:lts

RUN apt-get update && apt-get install -y yarn
WORKDIR /var/www
CMD  yarn install ; yarn docker-run
EXPOSE 80
