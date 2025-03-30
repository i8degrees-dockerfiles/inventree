
# InvenTree

## TODO

- [ ] ensure that we only add the `traefik-proxy` network to the services
that explicitly require it
  * `compose.yml`

- [ ] relocate `inventree-data` dir to our bind mount hierarchy
  * `./mounts/config`
    * `./mounts/config/config.yml`
    * `./mounts/config/nginx.conf`
    * `./mounts/config/secret_key.txt`
  * `./mounts/static`
  * `./mounts/media`
  * `./mounts/pgdb`
  * `./mounts/logs`

