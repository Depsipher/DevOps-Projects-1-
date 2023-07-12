# Step 2 - Installing MySQL
Now that the server is functioning properly, it's time to install my MySQL. MySQL is a renowned relational database management system used within PHP environments.

Use the 'apt' command to install MySQL

```
sudo apt install mysql-server
```

When completed log into MySQL by using the following command

```
sudo mysql
```
This will connect to MySQL as the admin database root user and should look like this
![sudo mysql](https://github.com/Depsipher/DevOps-Projects-1-/assets/138725118/53b2243f-2ab1-4afe-8027-3195664a2945)

Security is always priority so it's always recommened to run a security script that comes pre-installed with MySQL. The script removes insecure default setting and locks aodn access to the database system.

```
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'PassWord.1';
```
Exit MySQL
```
mysql> exit
```
Start the interactive script
```
sudo mysql_secure_installation
```

![sudo mysql_secure_install](https://github.com/Depsipher/DevOps-Projects-1-/assets/138725118/7dd437ef-2fcc-47b7-b401-7eb453a67868)

After running the command you can see that it'll show that VALIDATE PASSWORD COMPONENT can be used to test passwords and improve security.

You also see that there are three levels of password validation policy and then given the three levels. 

After taking the time to set a new password (or not), see if you can log in to MySQL
```
sudo mysql -p
```


![sudo mysql -p](https://github.com/Depsipher/DevOps-Projects-1-/assets/138725118/ea155843-efb4-49db-a554-b4fae6809dd7)

The -p flag will prompt you for the root password.

The MySQL server is now installed and secured. Next I'll install PHP, the final component in the LAMP stack.

