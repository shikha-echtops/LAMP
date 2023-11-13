### How to install LAMP

`sudo apt update`

### Installation
 -
```
$ sudo apt install apache2
$ sudo apt install mysql-server
$ sudo apt install php libapache2-mod-php php-mysql
```
### Config 
-
```
$ sudo nano /etc/apache2/sites-enabled/`your_domain`.conf
```
###### Paste the following configuration block.
```
 <VirtualHost *:80>
   ServerAdmin `shikha23@localhost`
   ServerName `your_domain`
   ServerAlias `www.your_domain`
   DocumentRoot /var/www/`your_domain`
   ErrorLog ${APACHE_LOG_DIR}/error.log
   CustomLog ${APACHE_LOG_DIR}/access.log combined
 </VirtualHost> 
```
###### Create the directory for ```your_domain```
```
$ sudo mkdir /var/www/`your_domain`
$ sudo chown -R $USER:$USER /var/www/`your_domain`
$ sudo chmod -R 755 /var/www/`your_domain`
$ nano /var/www/`your_domain`/index.html
```
###### Paste this in file HTML.
```
<html>
    <head>
        <title>Welcome to `Your_domain`!</title>
    </head>
    <body>
        <h1>Success!  The `your_domain` server block is working!</h1>
    </body>
</html>
```
##### Restart Apache web server
```
$ sudo systemctl restart apache2
$ sudo systemctl status apache2
```
###### Let's enable file with `a2ensite` tool:
```
$ sudo a2ensite `your_domain`.conf

