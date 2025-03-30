
# inventree

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

Finally, use your favorite text editor and begin filling in the
variables inside of each file to your liking. Once you are finished,
you may attempt to bootstrap the project!

```sh
compose up -d
# docker compose up -d
```
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

