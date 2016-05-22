# Izanagi

## Virtual machine bootstrapping scripts

Previously, I had multiple repos filled w/ Ansible scripts in
various states. Each had its own weird directory structure.
This repo was created to combine those repos and make things proper.
It's name is a nod to [Izanagi](http://naruto.wikia.com/wiki/Izanagi) from
[Naruto](naruto.wikia.com/wiki/).

## Included Roles

| Role Name        |  Description                            | Required Roles |
|------------------|-----------------------------------------|----------------|
| `photoserver`    | Lychee server                           | webserver      |
| `timemachine`    | Time Machine server                     |                |
| `webserver`      | Basic Apache web server                 |                |

## Ansible Variables

| Variable Name | Description                              | Default    |
|---------------|------------------------------------------|------------|
| `skip_update` | Do not run APT updates or upgrades       | `false`    |

## Assumptions

* All of these scripts are expected to be run on Ubuntu or another
  Debian derivative (e.g. Raspbian, Mint, etc).
* The remote user expectations:
  * can log in via SSH without a password
    * able to `sudo` without a password

# What I Usually Do First

Seems these are always the first three commands I run:

```
$ sudo apt-get install -y vim openssh-server
$ sudo vim /etc/sudoers
$ ssh-keygen
```

Next I copy the public key of whatever server I'm running Ansible from over.
After that, `sudo reboot` and get ready.
