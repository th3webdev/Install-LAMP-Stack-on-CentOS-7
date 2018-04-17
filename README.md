# Install LAMP Stack on CentOS 7

One to two paragraph statement about your product and what it does.


## Installation


### Install the Apache httpd server

```sh
yum -y install httpd
```


### Install PHP 7

```sh
rpm -Uvh https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
```

```sh
rpm -Uvh https://mirror.webtatic.com/yum/el7/webtatic-release.rpm
```

```sh
yum repolist
```

#### Install php7 and related package
```sh
yum -y install mod_php71w php71w-cli php71w-common php71w-mysqlnd php71w-mbstring
```


### Install MariaDB Database Server

```sh
yum -y install mariadb-server
```
#### Set MySQL root password

```sh
mysql_secure_installation
```

Insert your database password then write `y` for others options.

### Install MariaDB Database Server

Change into the `/usr/share` directory.

#### Download phpMyAdmin package

```sh
curl -O https://files.phpmyadmin.net/phpMyAdmin/4.7.5/phpMyAdmin-4.7.5-all-languages.tar.gz
```

#### Rename the extracted folde

```sh
mv phpMyAdmin-4.7.5-all-languages phpmyadmin
```

#### Create apache configuration file

Then copy the content of `phpmyadmin.conf`, create and past into the new file `/etc/httpd/conf.d/phpmyadmin.conf`.

```sh
vim /etc/httpd/conf.d/phpmyadmin.conf
```

### Restart the services

#### Apache server

```sh
systemctl restart httpd
```

#### Mariadb server

```sh
systemctl restart mariadb
```


* PHP Version: 7.1

* Comming soon:
    * Virtual hosts over CentOS 7
