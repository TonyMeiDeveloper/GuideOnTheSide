#Step 2: Deploy Guide on the Side

In this guide, we will begin deploying Guide on the Side to our virtual server. I assume you already connected to your virtual server and installed Apache. 

##Configuring Apache Server

Use cd ../ or cd .. command a bunch of times to go back in directories and use ls to make sure you are in the root directory. Yours should look like this:

```
cd ../
```


![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/apache1.png)


Navigate to /etc/apache2 directory

```
cd etc/apache2
ls
```


![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/apache2.png)


Open the Apache2 config file

```
sudo vim apache2.conf
```

Scroll down the contencts of the file until you see this:


![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/apache3.png)


To edit a file in vim, press Insert on Windows or press i on Mac to be in insert mode of the file.

Change it so it would look like this:


![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/apache4.png)


Press Escape button to exit Insert Mode. Then type in :wp and Enter/Return to save and exit the file. 


![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/apache5.png)


Once you exit out of the config file, restart Apache server to apply changes.
```
sudo service apache2 restart
```

##Download Guide on the Side and CakePHP

Next, we should download Guide on the Side. Navigate to /var/www/html.


![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/gos1.png)


Before cloning Guide on the Side, you need to install and update git.
```
sudo apt-get install git
```


![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/gos2.png)


Clone Guide on the Side project. 
```
sudo git clone https://github.com/ualibraries/Guide-on-the-Side.git guide_on_the_side
```


![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/gos3.png)


Guide on the Side Web Application requires CakePHP library. 
```
sudo git clone -b 2.x git://github.com/cakephp/cakephp.git 
```


![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/gos4.png)


Move CakePHP into Guide on the Side. You should see a lib folder in guide_on_the_side or at least Cake in some of the folders
```
sudo mv cakephp/app/Lib guide_on_the_side/
```


![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/gos5.png)


##Configure MySQL

Login to MySQL. If it doesn't work try sudo mysql –u root –p

```
mysql –u root –p
```

![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/gos6.png)


Create a MySQL database for Guide on the Side. Tutorials and data have to be stored somewhere. 
```
CREATE DATABASE guide_on_the_side;
```
Then add a user and password associated with the database. 
```
GRANT ALL ON guide_on_the_side.* TO gots_user@localhost IDENTIFIED BY 'my_password';
```

![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/gos7.png)


Exit MySQL. 
```
exit
```


##Configuring Guide on the Side

We should configure a config file in Guide on the Side. Copy config.sample.yml to a new file config.yml.
```
sudo cp config.sample.yml config.yml 
```


![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/gos8.png)


Open and edit config.yml. And fill in login and password and database. That's all the changes I made to the config file
```
sudo vim config.yml
```


![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/gos9.png)


Next, we install database schema and samples. Navigate to guide_on_the_side/app directory. Enter:
```
sudo ../lib/Cake/Console/cake Migrations.migration run all --plugin Tags
```

![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/gos10.png)

Next command:
```
sudo ../lib/Cake/Console/cake Migrations.migration run all
```


![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/gos11.png)

Another command:
```
sudo ../lib/Cake/Console/cake gots add_demo_tutorials
```

Next, we need to change permissons so that the web application can access/edit files in certain folders. Navigate back to the guide_on_the_side directory.
```
sudo chmod -R 777 app/tmp
sudo chmod -R 777 app/webroot/uploads
```

![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/gots12.png)


This is something I found out that isn't covered in the Guide on the Side documentations.

What I did was 

```
sudo a2enmod rewrite 
sudo service apache2 restart
```

The command disables directory listing of files when you view the page on a web browser. For more information about the command: http://www.jarrodoberto.com/articles/2011/11/enabling-mod-rewrite-on-ubuntu

![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/works1.png)


##See if it works

Get the public DNS of your virtual server.


![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/works2.png)


Go on your browser and go to PublicDNS/guide_on_the_side into the web browser.


![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/works3.png)


If you see guide on the side, congrats!

Go to PublicDNS/guide_on_the_side/admin or login to access/edit/add tutorials! 
Default Username: admin      
Default Password: GuideOnTheSideAdmin#1     


![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/works4.png)




![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/works5.png)


This guide was based from the Guide of the Side documentation:
https://github.com/ualibraries/Guide-on-the-Side/blob/master/README.md#about

Keep in mind, I made several adjustments in this guide that's different to accommodate Amazon Web Servcies and ease of use.

I haven't covered security here. I'll leave that up to you. 













