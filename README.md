# Install Compose V2 Plugin to Snap Installed Docker
Notes about installing compose v2 plugin to docker when it is installed from Snap. 

> This instructions are made by merging info from: [docs.docker.com > compose-plugin](https://docs.docker.com/compose/install/compose-plugin/) with  [forum.snapcraft.io > Is it possible to run docker cli plugins from the docker snap](https://forum.snapcraft.io/t/is-it-possible-to-run-docker-cli-plugins-from-the-docker-snap/16574).
#

1. To download and install the Compose CLI plugin, run:
```bash
DOCKER_CONFIG=~/snap/docker/current/.docker/
mkdir -p $DOCKER_CONFIG/cli-plugins
curl -SL https://github.com/docker/compose/releases/download/v2.6.0/docker-compose-linux-x86_64 -o $DOCKER_CONFIG/cli-plugins/docker-compose
```

This command downloads the latest release of Docker Compose (from the Compose releases repository) and installs Compose for the active user under the current snap docker directory.

2. Apply executable permissions to the binary:
```bash
 chmod +x $DOCKER_CONFIG/cli-plugins/docker-compose
```

3. Test the installation.
```bash
docker compose version
```

The result must be similar to: `Docker Compose version v2.6.0`.

I hope I help, please leave a star to know how many ppl helped by these instructions.
