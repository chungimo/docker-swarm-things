Netbox on Traefik
---
[The Github repository](https://github.com/netbox-community/netbox-docker) houses the components needed to build Netbox as a Docker container.

NetBox is an IP address management (IPAM) and data center infrastructure management (DCIM) tool. Initially conceived by the network engineering team at DigitalOcean, NetBox was developed specifically to address the needs of network and infrastructure engineers.

NetBox runs as a web application atop the Django Python framework with a PostgreSQL database. For a complete list of requirements, see requirements.txt. The code is available on GitHub.

This is a compose file to launch Netbox utilizing Traefik reverse proxy.

#### Setup
Configure these environment variables that sets the rules for Traefik.

Setup these environment variables:
```
export HOSTNAME=netbox.domain.com
export TRAEFIK_NETWORK=traefik-public
```

#### Nginx config by default storage driver
`/var/lib/docker/volumes/netbox_netbox-nginx-config/_data`

#### Docker stack deploy
`git clone -b master https://github.com/netbox-community/netbox-docker.git`

Copy this docker-traefik-netbox.yml file into the directory and deploy.

`docker stack deploy -c docker-netbox.traefik.yml netbox`
