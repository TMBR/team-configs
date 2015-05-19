# TMBR Configuration Files

This is a setup doc for local environments with the best way that we know how to utilize dynamic vhosts.

## System

Download [MAMP PRO](https://www.mamp.info/en/downloads/)

While it's downloading, do the following:

```
mkdir ~/tmbr/
sudo ln -s ~/tmbr/ /tmbr
cd ~/tmbr/
git clone git@github.com:TMBR/team-configs.git team-configs
ln -s ~/web ~/tmbr/web
```

After it's downloaded, complete the installation, and open MAMP PRO

## MySQL

- shut down any and all mysql servers (and vagrant box if it's running)
- Then the following:

```
cd /Library/Application\ Support/appsolute/MAMP\ PRO/db/
mv mysql mysql.orig
mv ~/mysql-data mysql
```

## MAMP PRO

### Apache Configuration

1. Go to File::Edit Template::Apache::httpd.conf
2. Below the other vhost configuration in the file (about 90% of the way down) add the following line:

```
Include /tmbr/team-configs/vhosts.conf
```

### General

1. Set ports to 80, 443, and 3306 (click the button)

### Hosts

![General](/screenshots/mamp/hosts-1.jpg?raw=true)
![Extended](/screenshots/mamp/hosts-2.jpg?raw=true)

### Modules

No Change

### PHP

![PHP Settings](/screenshots/mamp/php.jpg?raw=true)

### MySQL

![Screenshot](/screenshots/mamp/mysql.jpg?raw=true)

### Dynamic DNS

No Change

### Postfix

No Change

## Sequel Pro Config

Should look something like this

![Mamp Configuration](/screenshots/sequelpro/connection.jpg?raw=true)

You may need a password on your configuration -- YMMV

## Cleanup of old systems

### Homebrew MySQL

```
brew uninstall --force mysql
```

### Vagrant Box

TBD - once we have a good feeling that it's working.  It'll be something like:

```
vagrant destroy
```
