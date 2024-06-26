# Rails 7

This app Rails 7 with ruby 3.2.2, import maps, turbo, postgres, sidekiq, redis, stimulus and hotwire, all running in Docker.

## Requirements

Please ensure you are using Docker Compose V2. This project relies on the `docker compose` command, not the previous `docker-compose` standalone program.

https://docs.docker.com/compose/#compose-v2-and-the-new-docker-compose-command

Check your docker compose version with:
```
% docker-compose version
Docker Compose version v2.10.2
```

## Initial setup
```
cp .env.example .env
docker-compose build
docker-compose run --rm web bin/rails db:setup
```

## Running byebug 
```
docker attach [container_id]
```

## Running the Rails app
```
docker-compose up web 
```
Visit http://app.lvh.me/

## Running the Rails console
When the app is already running with `docker-compose` up, attach to the container:
```
docker-compose exec web bin/rails c
```

When no container running yet, start up a new one:
```
docker-compose run --rm web bin/rails c
```

## Updating gems
```
docker-compose run --rm web bundle update
docker-compose up --build
```

## How to use rail generators
New terminal
```
docker-compose up web 
```
New terminal
```
docker-compose exec web bash
-> root@7a886b07bb45:/usr/src/app# _
```

