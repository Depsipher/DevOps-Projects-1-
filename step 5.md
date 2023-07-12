# Step 5- Enable PHP on the Website
The default settings on Apache has the index.html file as the lead file by default and will always take precedence over index.php file. Since it takes precedence it will become the landing page for the application. 

If you want to change this behavior, you'll need to edit the /etc/apache2/mods-enabled/dir.conf file and change the order in which the index.php file is listed within the DircetoryIndex directive:
```
sudo vim /etc/apache2/mods-enabled/dir.conf
```
```
<IfModule mod_dir.c>
        #Change this:
        #DirectoryIndex index.html index.cgi index.pl index.php index.xhtml index.htm
        #To this:
        DirectoryIndex index.php index.html index.cgi index.pl index.xhtml index.htm
</IfModule>
```
After saving and closing the file, alway remember to restart the Apache server:
```
sudo systemctl reload apache2
```
Finally time to create the PHP script! This is when we test to verfiy that PHP is correctly installed and configured.

Create a new file named index.php inside the custom web root folder:
```
vim /var/www/projectlamp/index.php
```
Save & close the file, refresh the page, and the outcome should look something like this:

![PHP page](https://github.com/Depsipher/DevOps-Projects-1-/assets/138725118/8d54fdaa-078d-48e0-aed2-e73c666ad28c)

This page provide information about your server from the PHP perspective of PHP. It is useful for debugging and to ensure that your setting are being applied correctly.

This visual confirms that PHP is functioning as expected. 

After checking the relevant information about the PHP server it is best practice to remove the file to protect against the possibility of compromising sensitive information about the PHP environment and Ubuntu server. 

```
sudo rm /var/www/projectlamp/index.php
```
And just like that my very first PBL project is complete! I have successfully demonstrated how to deploy a LAMP stack website in AWS Cloud!!! 

