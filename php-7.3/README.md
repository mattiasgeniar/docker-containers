# PHP 7.3 Docker Image

What's included:
- A PHP 7.3 install compatible with most Laravel installations (with MySQL, intl, bcmath, imagick)
- Latest composer (1.9.0)

TO build & push:

```
$ docker build -t mattiasgeniar/php73 .
$ docker login && docker push mattiasgeniar/php73
```