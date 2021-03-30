# `docker-compose` on Linux #

SOME INFORMATION MAY NOT BE CORRECT ANY MORE

## Installation ##

Use the following command to download Docker Compose:

`sudo curl -L "https://github.com/docker/compose/releases/download/RELEASE/docker-compose-$(USER -s)-$(USER -m)" -o /usr/local/bin/docker-compose`

For example, at the time of this document's creation, the most recent stable release is 1.28.5.  To install, replace `RELEASE` with 1.28.5, and `USER` with your system user name:

`sudo curl -L "https://github.com/docker/compose/releases/download/1.28.5/docker-compose-$(linux1 -s)-$(linux1 -m)" -o /usr/local/bin/docker-compose`

check out the repo for docker compose [here](https://github.com/docker/compose/releases) for the most current stable release.

Then apply executable permissions to the binary:

`sudo chmod +x /usr/local/bin/docker-compose`

if `docker-compose` fails after installation, create a symbolic link to `/usr/bin`:

`sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose`

You're all set!  Test the installation to make sure it actually exists:

`docker-compose --version`

A line that looks like what follows should appear, where `RELEASE` is replaced with the release, and `BUILD#` is replaced with some non-base-10 number:

`docker-compose version RELEASE, build BUILD#`

## Compatibility ##

This is a list of Linux distros and their versions that are difinitively compatible with `docker-compose`.  There may be more distros that are compatible, or earlier versions that work.

### Ubuntu ###
compatible since >= 16.04

**NOTE:** For its siblings Kubuntu, Xubuntu, Lubuntu, etc., check the botton of this document.  At the writing of this documentation, Kubuntu is the only confirmed distro, though all Ubuntu siblings should generally be compatible >= 16.04

### Debian ###
compatible since >= 9.0

### Alpine Linux ###
compatible since >= 3.10

### Kali Linux / BackTrack ###
Kali Linux is based on Debian, so as long as you have >= Debian 9.0, you should be good.

**NOTE:** BackTrack is now Kali Linux, and has been since 2013; if you hope to use BackTrack, change over your distro to the most recent version of Kali Linux.

### Bodhi Linux ###
compatible since >= 5.0
Bodhi Linux is based on Ubuntu, so as long as you have >= Ubuntu 16.04, you should be good.

### BOSS (Bharat Operating Systems Solutions) Linux ###
BOSS Linux is based on Debian, so as long as you have >= Debian 9.0, you should be good.

### CentOS ###
compatible since >= 7

### CRUX ###
compatible since >= 3.4

### Devuan ###
Devuan is based on Debian, so as long as you have >= Debian 9.0, you should be good.

### Dragora GNU/Linux - Libre ###
all versions should be compatible

### Fedora ###
Fedora: compatible since >= 28, but [it's very complicated](https://techguidereview.com/install-docker-compose-fedora-32/).

Fedora Desktop Edition (64-bit) for Linux: unknown, but it should work with most versions; `docker-compose` typically works on 64-bit operating systems.

### Guix ###
compatible since >= 1.2.0

### Oracle Linux ###
compatible since >= 8, but [it's very complicated](https://dev.to/kylejschwartz/install-docker-compose-on-oracle-linux-8-1kb0).

### SUSE Linux Enterprise Server ###
compatible since >= 12

**NOTE:** Not compatible with open SUSE Leap or Tumbleweed.

### Void Linux ###
probably compatible with all versions.  Wiki + documentation have not been updated, but Wiki does say `docker-compose` can be installed with:

`xbps-install docker-compose`

Start and enable the service:

`ln -s /etc/sv/docker /var/service/`

Add user to docker group:

`sudo usermod -aG docker USER`

where `USER` once again replaces your username.

### Kubuntu ###
compatible since >= 16.04

## Final Notes ##

### Red Hat Enterprise Linux (RHEL) ###
incompatible <= 7.8

docker-compose is only compatible with 64-bit operating systems.  I wasn't able to find this information online, because the [official site](https://access.redhat.com/solutions/1586663) with that answer is blocked by a paywall. I hope this list saves you a bit of time in your development.
