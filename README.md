[![Docker Pulls](https://img.shields.io/docker/pulls/gnuton/asuswrt-merlin-toolchains-docker.svg)](https://hub.docker.com/r/gnuton/asuswrt-merlin-toolchains-docker)

# Asuswrt-Merlin-Toolchains-Docker
Docker images based on Ubuntu 16.04 and 20.04 containing Asuswrt Merlin BCM-SDK Toolchains.
You may wanna use this to build Asus Merling by yourself.

## Always up-to-date
The docker images are automatically built and published every night, so they are always up-to-date.

## Usage
The docker file contains ubuntu and toolchain needed to build HND and not HND firmware.

```bash
git clone ASUS_MERLIN_REPO_OR_ASUS_GPL
cd asuswrt-merlin.ng
docker pull gnuton/asuswrt-merlin-toolchains-docker:latest-ubuntu-20_04
docker run -it --rm -v "$PWD:/build"  -u $(id -u ${USER}):$(id -g ${USER}) \
       gnuton/asuswrt-merlin-toolchains-docker:latest-ubuntu-20_04 /bin/bash
docker$ source /etc/profile
if the above doesn't work log out and launch again docker run
but this time run
docker$ source /home/docker/.profile

```

Now follow the instructions in the README file that you can find in the  Asus Merlin repository.

For more info please check the [Asus Merlin official repository](https://github.com/RMerl/am-toolchains)

# Building and publishing the image
```bash
docker build . -t asuswrt-merlin-toolchains-docker:latest-ubuntu-20_04^C
docker push  gnuton/asuswrt-merlin-toolchains-docker:latest-ubuntu-20_04
```
