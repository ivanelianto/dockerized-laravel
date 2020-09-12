## Dockerized Laravel

Dockerized Laravel is a laravel application with docker configured.

## System Requirements
- Docker
- Docker Compose

## How to use?
1. Clone the repository
2. Copy `.env.development` to `.env`
3. Fill in `.env` file with `DB_DATABASE`, `DB_USERNAME`, and
   `DB_PASSWORD` environment values
4. Execute command `docker-compose build app`, to build application
   image
5. Execute command  `docker-compose run --rm composer install`, to
   install application depedencies

## How to contribute?
Any kind of contribution are welcome.

## Contributors
- [ivanelianto](https://github.com/ivanelianto)
