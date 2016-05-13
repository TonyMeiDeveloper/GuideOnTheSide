#Putty SSH

Download Putty and Puttygen 
http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html

##Puttygen

Puttygen is a program that converts the .pem key you downloaded into .ppk format which works with Putty. 

Open up Puttygen. The Type of Key should be SSH-2 RSA and number of bits should be 1024.


![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/puttygen1.png)


Next, click Load to load an existing private key file. Select your key which should be .pem. Be sure to click on All Files to see your key.pem. 


![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/puttygen2.png)


After you load your .pem private key. Click on Save Private key under the Load button. I haven't put in a key passphrase, but you can try it. 


![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/puttygen3.png)


Save the new key as .ppk. .ppk works for Putty. Exit out of Puttygen. 


![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/puttygen4.png)


##Putty

To connect using Putty you need a hostname. The Hostname is username@public_dns_name. I'm using Ubuntu so username is Ubuntu. Find other usernames at http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/putty.html. 

To find the public_dns_name of your instance server, go on the instance dashboard and at the bottom under description is the Public DNS. Copy that. 


![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/publicdnsname.png)


