FROM ubuntu:20.04

USER root

WORKDIR /app

COPY package*.json ./

RUN apt-get update

RUN apt-get install -y curl gnupg

RUN curl -sL https://deb.nodesource.com/setup_18.x | bash -

RUN apt-get install -y nodejs

RUN npm install -g npm@latest

RUN npm install

COPY . .

EXPOSE 7000

CMD ["node","server.js"]
