# STEP 4 - Creating a Virtual HOst For Your Website Using Apache
I will set up a domain called projectbelieve.

The /var/www/html directory has one server block enabled by default that serves documents.

Create the directory for projectbelieve using the `mkdir` command
```
sudo mkdir /var/www/projectbelieve
```
Next, assign ownership of directory to current user:
```
sudo chown -R $USER:$USER /var/www/projectbelieve
```


![virtual host create](https://github.com/Depsipher/DevOps-Projects-1-/assets/138725118/c22d14a8-0427-4f48-ab4d-a25fc9bcade6)

NOTE: I ran the `ls -ld` command to verify the ownership was changed


Then, create a new configuration file in Apache's sites-available directory using vim (or youer preferred command-line editor)
```
sudo vi /etc/apache2/sites-available/projectlamp.conf
```

This will create a new blank file. Paste the following text by pressing the letter i on the keyboard and pasting this:
```
<VirtualHost *:80>
    ServerName projectlamp
    ServerAlias www.projectlamp 
    ServerAdmin webmaster@localhost
    DocumentRoot /var/www/projectlamp
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```
To save and close the file do the following steps:
1. Press the esc button
2. Type :
3. Press wq. (w for write q for quit)
5. Press ENTER and the file will then save

Now I'll use the `ls` command to show the new file in the sites-available directory
```
sudo ls /etc/apache2/sites-available
```
It will look something like this

![ls command ](https://github.com/Depsipher/DevOps-Projects-1-/assets/138725118/d49a389d-89d9-424a-b2da-c1e3ffed411d)


Now I can use the `a2ensite` command to enable the virtual host

To make sure the configuration file contains no syntax errors run:
```
sudo apache2ctl configtest
```
Lastly, reload Apache so these changes take effect
```
sudo systemctl reload apache2
```

The website is now active! The web root /var/www/projectlamp is still empty though. Create an index.html file in that location so that we can test that the virtual host works as expected:
```
sudo echo 'Hello LAMP from hostname' $(curl -s http://169.254.169.254/latest/meta-data/public-hostname) 'with public IP' 
$(curl -s http://169.254.169.254/latest/meta-data/public-ipv4) > /var/www/projectlamp/index.html
```
Now I'll go to the browser and try to open the website URL using the IP address:
```
http://54.235.16.242:80
```
This is what it looked like


![apache server](https://github.com/Depsipher/DevOps-Projects-1-/assets/138725118/4f5c6957-128c-41c1-94e7-df935a4d9fd3)

I will this as a temporary landing page for my application until I setup an index.php file to replace it. 
Always remember to remove or rename the index.html file from the document root. It take precedence over an index.php file. 



