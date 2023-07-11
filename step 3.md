# STEP 3- Installing PHP
Now that Apache is installed to serve content & MySQL to store and manage data, It's time to bring PHP in the fold to process code and display dynamic content.
In addition, I'll need php-mysql. This is a PHP module that allows PHP to converse with MySQL-based databases.
I'll also need libapache2-mod-php to allow Apache to deal with PHP files.

To install the three packages at once use the following command:
```
sudo apt install php libapache2-mod-php php-mysql
```
Once install is complete, utilize the following command to find out which version of PHP was installed
```
php -v
```
![php -v](https://github.com/Depsipher/DevOps-Projects-1-/assets/138725118/afd909b3-912a-45a3-88cd-b26f98cfa10e)

The LAMP stack is completely installed & fully operational! Remember LAMP stands for:

- Linux (In this case Ubuntu)
- Apache
- MySQL
- PHP

The best way to test PHP script is to set up a proper Apache Virtual Host to hold the website's files and folders. That's because it allows multiple websites on one machine without users noticing.


