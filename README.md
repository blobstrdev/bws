# bws
```shell
sudo apt-get install libapache2-mod-security2
```


Once the module is installed, you can modify the Apache config under the file `/etc/apache2/apache2.conf` Add this line around the end of the file.

```shell
<IfModule mod_security2.c>
SecServerSignature "Supa Serva"
</IfModule>
```

Install php after apache

```shell
sudo apt update
sudo apt install -y lsb-release ca-certificates apt-transport-https software-properties-common gnupg2

```

## Add the PHP packages APT repository to your Debian server.

```shell
echo "deb https://packages.sury.org/php/ $(lsb_release -sc) main" | sudo tee /etc/apt/sources.list.d/sury-php.list
```

## Import repository key:
wget -qO - https://packages.sury.org/php/apt.gpg | sudo apt-key add -

```shell
sudo apt update 
sudo apt install php8.0
```

## Installing modules
```shell
sudo apt install php8.0-{mysql,cli,common,imap,ldap,xml,fpm,curl,mbstring,zip}
```


Hiding PHP
Open the file `/etc/php/{version}/apache2/php.ini` and search for expose_php. Set this property to off.

expose_php = Off
Restart/Reload the web server and the X-Powered-By header will no longer be available. 

