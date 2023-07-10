# Step 1 - Installing Apache & Updating the Firewall 

Intall Apache using Ubuntu's package manager 'apt':

```

#update a list of packages in package manager
sudo apt update

#run apache2 package installation
sudo apt install apache2
```


![project1 sudo apt install apache2](https://github.com/Depsipher/DevOps-Projects-1-/assets/138725118/46fa4e4b-7ab6-43b6-ab81-9f795133d193)


To verify that apache2 is running as a Service in our OS, use following command

```
sudo systemctl status apache2
```



![project 1 systemctl status apaches2](https://github.com/Depsipher/DevOps-Projects-1-/assets/138725118/b248ed4a-b3bd-48f2-bde5-268345b033a1)

If it's green we are good to go!

Before traffic can be received by the server, TCP port 80 (the default port for web access) must be open.

We need to add a rule to EC2 configuration to open inbound connection through inbound port 80. So we'll try the following command

```

curl http://localhost:80
```


![curl localhost 80](https://github.com/Depsipher/DevOps-Projects-1-/assets/138725118/c0c54b78-f709-4efc-8d9f-21c8e6bf2465)

If the output looks something like it means our Apache web server responds to the curl command properly with some payload.

Now it's time to verify that the Apache server can respond to requests from the Internet. I opened a brower and attempted to access via URL. 



![verify web server is active](https://github.com/Depsipher/DevOps-Projects-1-/assets/138725118/b976b054-0f64-433c-8d85-20520c1f4dc3)

This Apache Ubuntu Default Page is proof that the web server is correctly installed and accessible through the firewall!
