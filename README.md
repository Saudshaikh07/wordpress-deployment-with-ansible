Deployment of WordPress Environment

1. Become root user on the master machine and creat inventory

![](Aspose.Words.c96ed7b5-c08e-4240-9a9f-7129b7dfc91d.001.png)

2. Install Dependencies for Wordpress

● Following guide from here -

<https://ubuntu.com/tutorials/install-and-configure-wordpress#1-overview>

Create a wordpress\_setup\_cep2.yaml playbook in the cep2 directory and create the following tasks in the playbook

![](Aspose.Words.c96ed7b5-c08e-4240-9a9f-7129b7dfc91d.002.jpeg)

![](Aspose.Words.c96ed7b5-c08e-4240-9a9f-7129b7dfc91d.003.jpeg)

3. Install and configure WordPress

Added the below tasks in the yaml file

![](Aspose.Words.c96ed7b5-c08e-4240-9a9f-7129b7dfc91d.004.jpeg)

![](Aspose.Words.c96ed7b5-c08e-4240-9a9f-7129b7dfc91d.005.jpeg)

4. Configure Apache for WordPress

First create a wordpress.conf file on the master machine Add the following code:

<VirtualHost \*:80>

DocumentRoot /srv/www/wordpress <Directory /srv/www/wordpress>

Options FollowSymLinks

AllowOverride Limit Options FileInfo DirectoryIndex index.php

Require all granted

</Directory>

<Directory /srv/www/wordpress/wp-content>

Options FollowSymLinks

Require all granted

</Directory>

</VirtualHost>

and then copy the file to the wordpress machine using the below task and also run the commands to correct the configurations

![](Aspose.Words.c96ed7b5-c08e-4240-9a9f-7129b7dfc91d.006.jpeg)

![](Aspose.Words.c96ed7b5-c08e-4240-9a9f-7129b7dfc91d.007.png)

5. Configure database

Create Mysql Database, create users and add the correct data to wp-config.php file

![](Aspose.Words.c96ed7b5-c08e-4240-9a9f-7129b7dfc91d.008.jpeg)

After running this yaml file

Wordpress installation done!!

![](Aspose.Words.c96ed7b5-c08e-4240-9a9f-7129b7dfc91d.009.png)

![](Aspose.Words.c96ed7b5-c08e-4240-9a9f-7129b7dfc91d.010.jpeg)
