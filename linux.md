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

#### Install LAMP Server
This is a shortened approach using a package that includes Apache, MySQL, and PHP
```shell
# Install lamp-server package
apt-get install lamp-server^

# Install PhpMyAdmin
apt-get install phpmyadmin

# Link PhpMyadmin to the Apache server
ln -s /etc/phpmyadmin/apache.conf /etc/apache2/conf-enabled/phpmyadmin.conf

# Restart Apache server
/etc/init.d/apache2 reload
```

<br> 

To test that the LAMP stack was successfully installed, simply enter the hosting server IP address into a browser. It should show you the default Apache page.
<p align="center"><img src="https://image.ibb.co/ch07Gx/Screen_Shot_2018_04_27_at_7_49_05_AM.png" width="500"></p>

<br>

To test that PhpMyAdmin was successfully installed, simply go to `<ip address>/phpmyadmin`. It should show you the PhpMyadmin login page.
<p align="center"><img src="https://image.ibb.co/fms9UH/Screen_Shot_2018_04_27_at_8_11_55_AM.png" width="500"></p>

<br>
