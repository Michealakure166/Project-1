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
