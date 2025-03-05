# Testcloud ☁️👩🏻‍🔬☁️

A simple setup which consists of a [Nextcloud](https://hub.docker.com/_/nextcloud) and [MariaDB](https://hub.docker.com/_/mariadb) containers.
This is targeting macOS with Docker Desktop installed.

## Use Case

I frequently need a fresh and local Nextcloud deployment for:

* Reproducing reported problems around Nextcloud or its client apps in scope of customer support
* Trying out Nextcloud features
* Running automated client app tests with clean servers, in example Xcode UI tests

⚠️ **Do not use this in production or public!**
This is intended for use on developer devices within a local and secure network only.

## Features

* A **script** for convenient control.
* Nextcloud exposed to host port **8080**.
* MariaDB exposed to host port **8306**.
* Passwords are `password` by default. See [compose.yml](compose.yml) for further details.

## How to Use

[The included Zsh script](bin/testcloud) simplifies handling a lot.
It takes at least one argument to know what to do.
To improve convenience even further, adding the [`bin`](bin/) directory to your `PATH` makes the script available independent from your current working directory.

```sh
export PATH='$PATH:~/path/to/this/bin'
```

### Starting

You can start the Testcloud with this. If it does not exist yet, it will be set up automatically.

```sh
$ testcloud start
```

If you would like to define a specific [Docker image tag](https://hub.docker.com/_/nextcloud/tags) for the Nextcloud image to use, you can do so through an environment variable.

```sh
$ NEXTCLOUD_TAG=30.0.5 testcloud start
```

### Dialing In

If you need to do so, you can open a shell directly as `www-data` in the Nextcloud web root inside the Docker container by issuing this:

```sh
$ testcloud shell
```

This is frequently necessary to interact with Nextcloud's command-line [`occ`](https://docs.nextcloud.com/server/latest/admin_manual/occ_command.html).

### Stopping

To shut everything down while still keeping the containers around:

```sh
$ testcloud stop
```

### Cleaning Up

To delete the containers completely without confirmation regardless of them running or not:

```sh
$ testcloud remove
```
