# gitbox

Runs a suite of services for a full-fledged GIT using Compose. Uses a bunch of a community-built Docker images.

## Services

- [Gitlab](https://hub.docker.com/r/gitlab/gitlab-ce)

## Getting started

### Prerequisite and dependencies

Install all dependencies list below on the server:

- [Nginx](https://www.digitalocean.com/community/tutorials/how-to-install-nginx-on-ubuntu-18-04-quickstart)
- [Certbot](https://certbot.eff.org)
- [Docker & Docker Compose](https://www.digitalocean.com/community/tutorials/comment-installer-et-utiliser-docker-sur-ubuntu-18-04-fr)
- [GIT](https://www.digitalocean.com/community/tutorials/how-to-install-git-on-ubuntu-18-04-quickstart)

### Clone the repository

Clone the repository on the server in the `home` directory.

### Change permissions

Change permissions of all service directories to add the group `docker`:

```
chown <user_name>:docker gitlab
```

### Edit the .env file

By default `.env` file is not versioned, run the following command to duplicate `.env.dist` and fill the file:

```
cp .env.dist .env
```

Update corresponding variables:

- `RESTART_MODE` - Docker restart mode
- `TIME_ZONE` - Time zone of containers
- `HOST_NAME` - Domain attach to the server

Like the following example:

```
RESTART_MODE=unless-stopped
TIME_ZONE=Europe/Paris
HOST_NAME=domain.com
```

## Start the Docker Compose 🚀

Simply start all the services with the commands below, which uses the `docker-compose.yml` file by default.

```bash
# -d option let you run containers in the background
docker-compose up -d
```

## Licence 🤞

`git-box` is licensed under the [MIT License](http://opensource.org/licenses/MIT).

Created with ♥ by [@yoriiis](http://github.com/yoriiis).
