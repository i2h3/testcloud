# Testcloud ☁️👩🏻‍🔬

A simple setup which consists of a [Nextcloud](https://hub.docker.com/_/nextcloud) and [MariaDB](https://hub.docker.com/_/mariadb) containers.
This is targeting macOS with Docker Desktop installed.

## Use Case

I frequently need a fresh and local Nextcloud deployment for:

* Reproducing reported problems around Nextcloud or its client apps
* Trying out Nextcloud features
* Running automated client app tests with clean servers

⚠️ **Do not use this in production or public!**
This is intended for use on developer devices within a local and secure network only.

## Features

* Nextcloud is exposed to the host on port **8080**.
* MariaDB is exposed to the host on port **8306**. This way it can be conveniently accessed with clients like [Sequel Ace](https://sequel-ace.com) for easier interaction.
* Passwords are `password` by default. See [compose.yml](compose.yml) for further details.
* Zsh scripts for convenient control because I cannot always remember the Docker commands.

## How to Use

1. `start.sh` to start up.
2. `shell.sh` (optional) to quickly get a shell as www-data inside the container for executing Nextcloud's command-line [`occ`](https://docs.nextcloud.com/server/latest/admin_manual/occ_command.html).
3. `stop.sh` to shut down.
4. `remove.sh` to clean up.