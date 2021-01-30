# Building Laravel with Docker

# Requirements

* Composer

# How project is created

  ```sh
  # Create Laravel 8.25.0 project in folder `docker-laravel`
  composer create-project laravel/laravel docker-laravel

  # Enter newly created folder
  cd docker-laravel
  mkdir docker

  # Create docker related files
  # docker-compose.yml at root
  # Configuration files in `/docker`
  # Minimal setup requires:
  #   • /docker/apache/apache.conf
  #   • /docker/debian/Dockerfile
  #   • /docker/php/php.ini
  # Add docker environment variables to `/.env` file

  ```


# Installation

* Copy `/.env.example` to `/.env`, make configuration changes to section below `Docker Setup` if necessary

  ```sh
  # Build docker image
  docker-compose build
  # Use `docker-compose build --no-cache` to rebuild from scratch
  # To check instructions with added environment variables `docker-compose config`

  # Start server
  docker-compose up

  # Visit website
  http://<docker machine ip>:<DOCKER_WEB_PORT_NUMBER specified in /docker/.env>

  # Attach bash terminal to web
  docker exec -ti <DOCKER_WEB_CONTAINER_NAME> bash
  # cd /var/www/html to run artisan commands

  # Stop server
  docker-compose down
  ```


# Resources

* Environment variables in Compose: https://docs.docker.com/compose/environment-variables/

* MySQL docker configurations: https://hub.docker.com/_/mysql