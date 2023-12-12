# Documentation of Project 1

## Installing Apache and Updating the Firewall
### Update a list of packages in package manager
`sudo apt update`

![package update](./Images/sudo-apt-update.png)

### Run apache2 package installation
`sudo apt install apache2`

![apache2 installation](./Images/sudo-apt-install-apache2.png)

### To verify Apache2 running status
`sudo systemctl status apcahe2`

![apache status](./Images/sudo-systemctl-status-apache2.png)

### Accessing webserver from Ubuntu shell
`curl http://localhost:80`

![accessing webserver locally](./Images/webserver-from-ubuntu-shell.png)

### Accessing webserver over the internet
`http://54.87.226.229:80`

[Apache2 Ubuntu Default Page](http://http://16.16.68.188/)

![webserver over the internet](./Images/apache2-ubuntu-default-page.png)

## Installing mysql

### Running mysql installation
`sudo apt install mysql-server`

![installing mysql](./Images/installing-mysql.png)

### Logging on to mysql console

`sudo mysql`

![mysql console](./Images/mysql-console.png)

### Running pre-installed mysql security script

`ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'xxxxxx';`

![security script](./Images/running-security-script.png)

### Validate Passwword Plugin

`sudo mysql_secure_installation`

![validate password plugin](./Images/validate-password-plugin.png)

### Confirming logon to mysql console

`sudo mysql -p`

![logon confirmation](./Images/confirming-logon-to-mysql.png)

## Installing PHP

### Installing the php package, php-mysql and libapache2-mod-php

`sudo apt install php libapache2-mod-php php-mysql`

![installing PHP](./Images/installing-php.png)

### Confirming PHP version

`php -v`

![PHP version](./Images/php-version.png)


## Creating Virtual Host for Website Using Apache

### Setting up a doamin called projectlamp

### creating directory for projectlamp

`sudo mkdir /var/www/projectlamp`

![making projectlamp directory](./Images/making-projectlamp-directory.png)

### Assigning ownership of the directory to current system user

`sudo chown -R $USER:$USER /var/www/projectlamp`

![assigning ownership of directory](./Images/ownership-of-directory.png)

### Creating and opening a new configuration file in Apache’s sites-available directory using vi

`sudo vi /etc/apache2/sites-available/projectlamp.conf`

![configurattion file](./Images/config-file.png)

### The following bare-bones configuration was used


![bare-bones configuration](./Images/bare-bones-config.png)

### Using ls command to show new file in the sites-available directory

`sudo ls /etc/apache2/sites-available`

![new file in sites-available directory](./Images/ls-command-sites-available.png)

### Enabling new virtual host

`sudo a2ensite projectlamp`

![new virtual host](./Images/enabling-new-host.png)

### Disabling Apache default website

`sudo a2dissite 000-default`

![disable default website](./Images/disable-default.png)

### To confirm configuration file doesn’t contain syntax errors

`sudo apache2ctl configtest`

![syntax OK](./Images/syntax-ok.png)

### reloading Apache to effect changes

`sudo systemctl reload apache2`

![effecting changes on apache](./Images/reload-apache.png)

### Creating an index.html file in web root /var/www/projectlamp

`sudo echo 'Hello LAMP from hostname' $(curl -s http://169.254.169.254/latest/meta-data/public-hostname) 'with public IP' $(curl -s http://169.254.169.254/latest/meta-data/public-ipv4) > /var/www/projectlamp/index.html`

![creating index file](./Images/web-root.png)

### Opening website from browser with public IP Address

[website with public IP](http://54.87.226.229:80)

![website from browser over internet](./Images/echo.png)



## Enabling PHP on website
### Making index.php have precedence over index.html

`sudo vim /etc/apache2/mods-enabled/dir.conf`

![prioritizing index.php](./Images/php-html.png)


### the following config was saved

![config used](./Images/indexphp-config.png)

### Reloading Apapche to effect changes

`sudo systemctl reload apache2`

![effecting changes on apache](./Images/reload-apache.png)

### Creating file named index.php inside custom web root folder

`vim /var/www/projectlamp/index.php`

![new index.php file inside custom root folder](./Images/new-index-php.png)

### PHP code saved for file configuration

![php code config saved](./Images/php-code-saved.png)

### Refreshing the webpage on internet browser provides php server info

![php server info](./Images/php-page.png)

### Deleting index.php due to sensitive info displayed

`sudo rm /var/www/projectlamp/index.php`

![removing index file created](./Images/remove-index-file.png)

# PHP installation is complete, web service is operational

# Project One Complete: Deployment of LAMP stack website in AWS Cloud!
