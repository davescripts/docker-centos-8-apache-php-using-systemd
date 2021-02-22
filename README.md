# Docker Container: Centos8, Apache, and PHP, using systemd

Dockerfile for a Container with Centos 8, Apache, and PHP, using systemd, for Web Development.

More details can be found [here](https://davescripts.com/docker-container-with-centos-8-apache-php-using-systemd).

<br>

## Build

Create Docker Image.

```sh
docker build -t <image_name> .
```

_Replace **&lt;image_name&gt;** with the name you want for the image._

<br>

Example.

```sh
docker build -t image_centos8 .
```

<br>

## Run

Create Docker Container.

```sh
docker run -tid -p 4000:80 --name=<container_name> --tmpfs /run -v /sys/fs/cgroup:/sys/fs/cgroup:ro -v /path_to/folder:/var/www/html <image_name>
```

_Replace **&lt;container_name&gt;** with the name you want for the container, and **&lt;image_name&gt;** with the name of the image you specified on the Build command above._

<br>

Example.

```sh
docker run -tid -p 4000:80 --name=container_centos8 --tmpfs /run -v /sys/fs/cgroup:/sys/fs/cgroup:ro -v /path_to/folder:/var/www/html image_centos8
```

_Also change **"/path_to/folder"** with the actual location of your website's root folder on your local machine._

<br>

## Test

Open the http://localhost:4000 url on your browser.
