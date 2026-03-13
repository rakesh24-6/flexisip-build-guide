# Installation Guide

This guide describes how to deploy Flexisip with an external database backend.

## System Requirements

Ubuntu Server 22.04

Recommended hardware:

CPU: 2 cores
RAM: 4 GB
Disk: 20 GB

---
Debian/Ubuntu

1. Create the Belledonne Communications APT repository

     in `/etc/apt/sources.list.d/belledonne.list`

## For Debian 9
```
deb [arch=amd64] http://linphone.org/snapshots/debian stretch stable # hotfix beta alpha
```

## For Debian 10
```
deb [arch=amd64] http://linphone.org/snapshots/debian buster stable # hotfix beta alpha
```

## For Debian 11
```
deb [arch=amd64] http://linphone.org/snapshots/debian bullseye stable # hotfix beta alpha
```

## For Ubuntu 18.04 LTS
```
deb [arch=amd64] http://linphone.org/snapshots/ubuntu bionic stable # hotfix beta alpha
```

## For Ubuntu 22.04 LTS
```
deb [arch=amd64] http://linphone.org/snapshots/ubuntu jammy stable # hotfix beta alpha
```

## For Ubuntu 24.04 LTS
``` 
deb [arch=amd64] http://linphone.org/snapshots/ubuntu noble stable # hotfix beta alpha
```
 or in `/etc/apt/sources.list.d/belledonne.sources` for recent distributions:

### For Debian 12
```
Types: deb
URIs: http://linphone.org/snapshots/debian/
Suites: bookworm
Architectures: amd64
### You may add 'hotfix' and/or 'beta' and/or 'alpha' to the components list
Components: stable
Signed-By: /usr/share/keyrings/belledonne-archive-keyring.gpg
```

### For Debian 13
```
Types: deb
URIs: http://linphone.org/snapshots/debian/
Suites: trixie
Architectures: amd64
# You may add 'alpha' to the components list
Components: beta
Signed-By: /usr/share/keyrings/belledonne-archive-keyring.gpg

You may add 'beta' and/or 'alpha' branches if you need access to pre-release and/or development packages, but keep in mind that stable branch must always be enabled because some external dependencies of Flexisip are provided through it.
```

2. Install Belledonne Communications PGP key for package signature checking
### For Debian until Debian 11
```
wget https://linphone.org/snapshots/debian/keyring.gpg -O - | sudo apt-key add -
```
### For Debian since Debian 12
```
wget https://linphone.org/snapshots/debian/keyring.gpg -O - | sudo gpg --dearmor -o /usr/share/keyrings/belledonne-archive-keyring.gpg
```

### For Ubuntu
``` 
wget https://www.linphone.org/snapshots/ubuntu/pubkey.gpg -O - | sudo apt-key add - 
```

3. Install development packages for the SQL back-end (example below for Mariadb, classic use case)

    *⚠ Not doing this can result in the following error: "[SOCI] connection pool open error: Failed to find shared library for backend mysql"*
```
apt install libmariadb-dev
```

4. Update APT cache and install Flexisip and its dependencies</br>
```
apt update
apt install bc-flexisip
```

## Install Dependencies

```
sudo apt update
sudo apt install flexisip mysql-server
```

---

## Verify Installation

```
flexisip --version
```

---

## Start Flexisip

```
sudo systemctl enable flexisip
sudo systemctl start flexisip
```

---

## Configuration Location

```
/etc/flexisip/flexisip.conf
```
