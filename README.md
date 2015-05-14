# TMBR Configuration Files

## System

Download [MAMP PRO](https://www.mamp.info/en/downloads/)

While it's downloading, do the following:

```
mkdir ~/tmbr/
sudo ln -s ~/tmbr/ /tmbr/
cd ~/tmbr/
git clone git@github.com:TMBR/team-configs.git team-configs
ln -s ~/web ~/tmbr/web
```

After it's downloaded, complete the installation, and open MAMP PRO

## MySQL

- shut down mysql server
- Then the following:

```
cd /Library/Application Support/appsolute/MAMP PRO/db/
mv mysql mysql.orig
mv ~/mysql-data mysql
```

## Apache

In MAMP go to File::Edit Template::Apache::httpd.conf

Below the other vhost configuration in the file (about 90% of the way down) add the following line:
```
Include /tmbr/team-configs/vhosts.conf
```

## Cleanup of old systems

### Homebrew MySQL

```
brew uninstall --force mysql
```
