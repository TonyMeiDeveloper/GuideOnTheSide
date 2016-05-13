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

##Guide on the Side Configurations

Next, we should download Guide on the Side. Navigate to /var/www/html.








