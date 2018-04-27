## Setup

### Links
| Name          | Link                                                            |
|---------------|-----------------------------------------------------------------|
| How to Deploy a Node.js App to DigitalOcean with SSL | https://code.lengstorf.com/deploy-nodejs-ssl-digitalocean/ |

<br>

#### Maintenance Commands
```shell
# Ensure all security updates are on system
# Get a list of all available updates
apt-get update

# Install all available updates
apt-get upgrade
```

<br>

#### Generate SSH Key
##### [ssh-copy-id](https://www.digitalocean.com/community/tutorials/ssh-essentials-working-with-ssh-servers-clients-and-keys)
```shell
# Generate SSH Key. Choose the name and location of the file. Pick a passphrase if desired.
ssh-keygen
```

<br>

#### Copy SSH Key to remote server
##### [ssh-copy-id](https://www.digitalocean.com/community/tutorials/ssh-essentials-working-with-ssh-servers-clients-and-keys)
```shell
# Copy public SSH Key to remote server. After typing in the password, the contents of your ~/.ssh/id_rsa.pub key will be appended to the end of the user account's ~/.ssh/authorized_keys file on the remote server
ssh-copy-id <username>@<remote_host>

# Login to the account on the server without a password
ssh <username>@<remote_host>
```

<br> 

##### [Without ssh-copy-id](https://www.digitalocean.com/community/tutorials/ssh-essentials-working-with-ssh-servers-clients-and-keys)
```shell
# Copy public SSH Key to remote server. The contents of your SSH Key file will be appended to the end of the user account's ~/.ssh/authorized_keys file on the remote server
cat ~/.ssh/<ssh key filename>.pub | ssh <username>@<remote_host> "mkdir -p ~/.ssh && cat >> ~/.ssh/authorized_keys"

# Login to the account on the server without a password
ssh <username>@<remote_host>
```

<br>

#### Install LAMP Server 

##### Install an all-in-one package
This is a shortened approach using a package that includes Apache, MySQL, and PHP
```shell
# Install lamp-server package
apt-get install lamp-server^

# Restart Apache server
/etc/init.d/apache2 restart
# Alternative syntax
systemctl restart apache2
```

<br>

##### [Install packages separately](https://howtoubuntu.org/how-to-install-lamp-on-ubuntu)
```shell
# Install Apache server
apt-get install apache2

# Install MySQL
apt-get install mysql-server

# Setup settings to require strong passwords for MySQL users (optional)
mysql_secure_installation

# Install PHP
apt-get install php5 libapache2-mod-php5

# Restart Apache server
/etc/init.d/apache2 restart
# Alternative syntax
systemctl restart apache2
```

<br> 

To test that the LAMP stack was successfully installed, simply enter the hosting server IP address into a browser. It should show you the default Apache page.
<p align="center"><img src="https://image.ibb.co/ch07Gx/Screen_Shot_2018_04_27_at_7_49_05_AM.png" width="500"></p>

<br> 

#### Install PhpMyAdmin
```shell
# Install PhpMyAdmin
apt-get install phpmyadmin

# Link PhpMyadmin to the Apache server
ln -s /etc/phpmyadmin/apache.conf /etc/apache2/conf-enabled/phpmyadmin.conf

# Restart Apache server
/etc/init.d/apache2 reload
```

<br> 

To test that PhpMyAdmin was successfully installed, go to `<ip address>/phpmyadmin`. It should show you the PhpMyadmin login page.
<p align="center"><img src="https://image.ibb.co/fms9UH/Screen_Shot_2018_04_27_at_8_11_55_AM.png" width="500"></p>

<br>
