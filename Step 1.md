# Step 1 - Installing Apache & Updating the Firewall 

Intall Apache using Ubuntu's package manager 'apt':

```

#update a list of packages in package manager
sudo apt update

#run apache2 package installation
sudo apt install apache2
```

To verify that apache2 is running as a Service in our OS, use following command

```
sudo systemctl status apache2
```

