
# InvenTree

Inventory management system

- [inventree/inventree:0.17.9][0]
- [Github: inventree repos](https://github.com/orgs/inventree/repositories?type=all)

## usage

First, we must prepare our local environment to suit this 
project by maintaining two files that should never be checked into
revision control -- `.env` and *especially* `.env.secrets`.

So, by using `.env.dist` and `.env.secrets.dist` as our two starting 
points:

```sh
cp -av .env.dist .env
cp -av .env.secrets.dist .env.secrets
```

Next, use your favorite text editor and begin filling in the
variables inside of each file to your liking. However you choose
to manage your credentials for this, be sure that the passwords
are kept somewhere safe!

```sh
INVENTREE_SITE_URL="http://inventory.fs1.home"
```

As I already have a private DNS setup on my LAN, I simply
visit my authoritative DNS panel and add an entry to the
**fs1.home** zone. Feel free to start off by using
**localhost** for this, orby adding an entry to your hosts
file at `/etc/hosts`.

```sh
# /etc/hosts
# Note that if you are using a reverse proxy that is hosted
# elsewhere, you may want to update the IP to reflect the
# address of the proxy host.
<hostIP> inventory.localhost
```

Finally, we can bootstrap the project! Cross your fingers, say
your prayers or however your typical ritual for this goes:

```sh
compose up -d
# docker compose up -d
# docker compose --env-file .env.secrets --env-file .env \
    # up -d
```

```sh
# Check status of each service
compose logs #--since=5m
```

- [IvenTree local instance](http://inventree.localhost)
- [IvenTree portal](https://inventree.fs1.home)

### apps

- [Git repo](https://github.com/inventree/inventree-app)
- [Build instructions](https://github.com/inventree/inventree-app/blob/master/BUILDING.md)

#### web

*...*

#### Android

- [Android Inventree App](https://play.google.com/store/apps/details?id=inventree.inventree_app)

#### iOS

- [iOS Inventree app](https://apps.apple.com/au/app/inventree/id1581731101#?platform=iphone)

## reference documents

[0]: https://hub.docker.com/r/inventree/inventree/tags
[1]: https://docs.inventree.org/en/stable/start/docker_install/#
[2]: https://raw.githubusercontent.com/inventree/inventree/0491b10438531221ccbcb08d271c5ba8e7c24d91/contrib/container/.env
[3]: https://raw.githubusercontent.com/inventree/inventree/0491b10438531221ccbcb08d271c5ba8e7c24d91/contrib/container/Caddyfile
[4]: https://raw.githubusercontent.com/inventree/inventree/0491b10438531221ccbcb08d271c5ba8e7c24d91/contrib/container/docker-compose.yml
[5]: https://docs.inventree.org/en/stable/app/app/#

1. [third party setup](https://github.com/Zeigren/inventree-docker)
1. [compose.yml: third-party setup](https://github.com/Zeigren/inventree-docker/blob/master/docker-compose.yml)
2. [inventree_nginx.conf: nginx conf](https://github.com/Zeigren/inventree-docker/blob/master/inventree_nginx.conf)
3. [traefik.yml: using traefik instead of Caddy](https://github.com/Zeigren/inventree-docker/blob/master/traefik.yml)
4. [production.yml: nginx with ssl](https://github.com/Zeigren/inventree-docker/blob/master/production.yml)

