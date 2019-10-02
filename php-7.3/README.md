# PHP 7.3 Docker Image

What's included:
- A PHP 7.3 install compatible with most Laravel installations (with MySQL, intl, bcmath, imagick)
- Latest composer (1.9.0)

# Using this container

You can refer to this container as `mattiasgeniar/php73`.

```
$ docker run -it --rm mattiasgeniar/php73 bash
php -v
PHP 7.3.10
```

# Build & Push

```
$ docker build -t mattiasgeniar/php73 .
$ docker login && docker push mattiasgeniar/php73
```