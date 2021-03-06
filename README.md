# Docker Laravel

A quick docker set up for [Laravel][laravel].

Includes PHP7, MySql, Redis, and nginx.

## Requirements

An installation of [Docker][docker] and [Docker Compose][docker-compose].

## Usage

Add the `docker-compose.yml` file and the `docker` directory of this repo to the root of your laravel app.

Now open the `docker-compose.yml` file and add replace `DB_NAME` and `DB_SECRET` with the correct options.

You will need to update your `.env` file to correspond with these changes.

```
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=33061
DB_DATABASE=DB_NAME
DB_USERNAME=root
DB_PASSWORD=secret
```

You will also need to update your `.env` file with the [redis][redis] config below.

```
CACHE_DRIVER=redis
REDIS_HOST=127.0.0.1
REDIS_PORT=63791
```

Once this is done run `docker-compose up`.

When the image has finished building you will be able to view your laravel app at `http://0.0.0.0:8080/`.

---

*The above set up is based off this [this][source] article*

[source]: https://kyleferg.com/laravel-development-with-docker/
[laravel]: https://laravel.com
[redis]: https://redis.io/
[docker]: https://store.docker.com/editions/community/docker-ce-desktop-mac
[docker-compose]: https://docs.docker.com/compose/install/
