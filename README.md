# vagrant-tve
Vagrant configuration for TVE developers
Based on PuPHPet (https://puphpet.com)

## Pre-requisites
- Install vagrant
- Install virtualbox

## Usage
- clone repo
- run `vagrant up`
- use `hosts` synced folder for your sites
- use `local.vagrant/adminer` for adminer (user: root, pass: root)
- use port 10000 for xdebug

## Known issues
### SSH connection fails on `vagrant up`
```
default: Error: Connection timeout. Retrying...
default: Error: Connection timeout. Retrying...
default: Error: Connection timeout. Retrying...
```
Solution: 
- Check `vagrant ssh-config` for ssh key location.
- Connect manually with username 'vagrant' and password 'vagrant':
`vagrant ssh` or `ssh vagrant@localhost:2222`
- add public key to `~/.ssh/authorized keys`
- `exit` and run `vagrant reload --provision`

### Hostupdater plugin is not working automatically now

Solution: insert this into your hosts file:
```
# vagrant
192.168.168.168 local.vagrant

# tve
192.168.168.168 local.tve.nbcuni.com
192.168.168.168 local.tve.bravo.nbcuni.com
192.168.168.168 local.tve.cnbc.nbcuni.com
192.168.168.168 local.tve.eonline.nbcuni.com
192.168.168.168 local.tve.esquire.nbcuni.com
192.168.168.168 local.tve.mun2.nbcuni.com
192.168.168.168 local.tve.nbcnews.nbcuni.com
192.168.168.168 local.tve.oxygen.nbcuni.com
192.168.168.168 local.tve.sprout.nbcuni.com
192.168.168.168 local.tve.syfy.nbcuni.com
192.168.168.168 local.tve.telemundo.nbcuni.com
192.168.168.168 local.tve.usa.nbcuni.com

# mvpd admin
192.168.168.168 local.mvpd-admin.nbcuni.com

# ott roku
192.168.168.168 local.roku.nbcuni.com
192.168.168.168 local.roku.usa.nbcuni.com
```
