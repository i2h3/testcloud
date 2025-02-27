# Testcloud ☁️👩🏻‍🔬

A simple setup which consists of a [Nextcloud](https://hub.docker.com/_/nextcloud) and [MariaDB](https://hub.docker.com/_/mariadb) container.

## Use Case

I frequently need a fresh and local Nextcloud deployment for:

* Reproducing reported problems around Nextcloud or its client apps
* Trying out Nextcloud features
* Running automated client app tests with clean servers

**Do not use this in production or public!**
This is intended for use on developer devices within a local and secure network only.

## Features

* Nextcloud is exposed to the host on port **8080**.
* MariaDB is exposed to the host on port **8306**. This way it can be conveniently accessed with clients like [Sequel Ace](https://sequel-ace.com) for easier interaction.
* Passwords are `password` by default. See [compose.yml](compose.yml) for further details.