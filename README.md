
# InvenTree

Inventory management system

- [inventree/inventree:0.17.10][0]
- [Github: inventree repos](https://github.com/orgs/inventree/repositories?type=all)

- contrib
  1. [inventree][0]
  2. [third party conf][6]

## usage

```sh
# cd ~/Projects
git clone \
    git@github.com:i8degrees-dockerfiles/inventree.git \
inventree.git
```

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

**WARNING:** If you receive an error regarding SSL handshake
and are using a self-signed certificate for the installation,
please try disabling SSL verification from within the app.

Finally, we can bootstrap the project! Cross your fingers, say
your prayers or however your typical ritual for this goes:

```sh
docker compose run --rm inventree-server invoke update
docker compose up -d
#docker compose down
#docker compose up -d --force-recreate
#docker compose up -d inventory-server --force-recreate
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

- Android & iOS
    - [GitHub: iventree-app](https://github.com/inventree/inventree-app)
    - [Build instructions](https://github.com/inventree/inventree-app/blob/master/BUILDING.md)

#### inventree-app

##### source tree

```sh
# ...From within your project root for my inventree 
# git repo (see usage above)
git submodule update --init --recursive
git submodule sync
cd "src/inventree-app.git"
```

*...*
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
[6]: https://github.com/Zeigren/inventree-docker

