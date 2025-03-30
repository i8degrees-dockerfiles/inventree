
# InvenTree

Inventory management system

- [inventree/inventree:0.17.9][0]
- [Github: inventree repos](https://github.com/orgs/inventree/repositories?type=all)

## usage

First, we must prepare our local environment to suit this
project by maintaining a local environment file called `.env`. This file must
never be checked into revision control! If you accidently push the file onto
a public medium, **all bits** considered sensitive must be discarded in full
and regenerated from scratch (by following this guide again).

So, without further ado, let us begin by creating our environment file by
using the existing template provided by us by [Inventree documentation][1].

```sh
cp -av .env.dist .env
```

Next, use your favorite text editor and begin filling in the
variables inside of each file to your liking. However you choose
to manage your credentials for this sort of thing, be sure that the
passwords are kept somewhere safe and accessible in the case that they may
need to be revoked at some point in the future.

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
<hostIP> inventree.localhost
```

Finally, we can bootstrap the project! Cross your fingers, say
your prayers or however your typical ritual for this goes:

```sh
docker compose up -d
docker compose down
```

```sh
# Check status of each service
docker compose logs #--since=5m

```sh
# Start and stop an individual service
docker start inventree-db # service name
docker stop inventree-proxy # service name
```

- [IvenTree local instance](http://inventree.localhost)
- [IvenTree portal](https://inventory.fs1.home)

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

