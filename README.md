# Plex Server Configuration

The docker-compose and environment files in this repo define a configuration for the following services:

- Plex
- Radarr
- Sonarr
- Jackett
- Tautulli
- Ombi (Requires reverse proxy)
- Deluge (with VPN attached)

> Note that all images but deluge are set to use the images from [LinuxServer.io](https://linuxserver.io).
> Deluge uses [the image created by binhex](https://github.com/binhex/arch-delugevpn)

## Installation

### Requirements
- Docker engine
- Docker-compose

### Instructions
1. Clone this repo:

   `git clone https://github.com/Laura7089/plexConfig`
2. Copy `.env.example` into `.env` and `vpn.env.example` into `vpn.env`
3. Populate these files with the options you desire, make sure to keep them exacty in the format `VAR=VAL`
4. Run `docker-compose up -d`

### Ombi and Plex Reverse Proxy
If you want to provide a reverse proxy pointing at the public services Ombi and Plex (if you want to use https, for example), you can place the container running it on the network you specified under `RP_NETWORK_NAME` for ease of routing using docker's hostname resolution.

I use [linuxserver's letsencrypt image](https://hub.docker.com/r/linuxserver/letsencrypt) for this.
