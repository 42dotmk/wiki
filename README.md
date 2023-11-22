# Base42 Wiki

This repo contains the configuration and setup for Base42's Wiki installation.

It's based on MediaWiki and MariaDB and uses Docker + Docker Compose to manage the environment.

## Prerequisites

You will need a Linux machine with Docker installed. You can probably make it work on Windows or MacOS without any changes, but we won't cover that here.


## Installation

- Clone the repo
- Copy `.env.example` and rename it to `.env`
- Modify the environment variables with your own
- Run `docker-compose up -d` to spin up the containers
- You should be able to access the MediaWiki installer on `http://localhost:8080`
- Follow the installation instructions to configure the instance to your needs (make sure to enter the same details for the DB as you did, and the host is not `localhost` but `db` - the name of the Docker service)
- After installation you will get a `LocalSettings.php`, download the file, place it into `volumes/mediawiki/LocalSettings.php` and uncomment the commented out volume that matches that path in `docker-compose.yml`
- Run `docker-compose up -d` again to attach the newly mounted volume
- Congrats, MediaWiki is now installed