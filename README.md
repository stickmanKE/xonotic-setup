# Xonotic Setup

## Download

Download the latest version from https://www.xonotic.org/download/

## Setup

### Dedicated Server setup (debian)

You will need to be root to install the server, simply copy&paste the following
commands:

```bash
curl -Lo- https://github.com/Thermondo/xonotic-setup/archive/master.tar.gz | tar xzf - -C /tmp
/tmp/xonotic-setup-master/install-debian-server.sh
```

It download and run an install script. The script will ask you about which
version to install.

The script will install Xonotic, `xmm` and a HTTP server to serve custom maps.
It will create the new `systemd` services `xonotic` and `xonoitc-maps`.
It will also create a new user named `xonotic` to isolate the installation.

You can install new maps via:

```
su xonotic -c "xmm install MAP_NAME"
# are you are do installing maps you will need to restart the server
systemctl restart xonotic
systemctl restart xonotic-maps
```

### Docker (server only)

```
docker pull detrate/xonotic-docker
docker run --name xonotic-server -d detrate/xonotic-docker:stable
```

See also: https://github.com/z/xonotic-docker

## Xonotic Map Manager

The [Xonotic Map Manager][xmm] allows you easily download new maps.

```
pip install xmm
xmm --help
```

You can seach maps via ```xxm search``` or via a web repo:
http://xonotic.co/

[xmm]: https://xonotic-map-manager.readthedocs.io/
