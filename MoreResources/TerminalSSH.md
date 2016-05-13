#SSH via Terminal

SSH via Terminal is pretty simple as AWS gives you a straight forward tutorial, but we do it anyway.

![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/connect.png)

If you using a Mac or Linux, search for Terminal. It should be preinstalled. I HOPE :)

![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/terminal1.png)


You should know some Terminal Commands that are commonly use.  
First is ls which lists and shows all the files and folders on your current directory. Note that after you entered a command, press enter/return to submit it. 

```
ls
```


![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/terminal2.png)


Next is cd. It changes your directory. Before, we downloaded the key. The key is in my downloads folder so cd Downloads to get to the Downloads directory. If the key downloaded is in your desktop. Do cd Desktop. ETC. 

```
cd Downloads
ls
```


![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/terminal3.png)


Once you located your key, we pretty much followed the instructions AWS gave us. Note that my key is example.pem.txt. Yours will be different. 

```
chmod 400 yourkey
ssh -i "yourkey" ubuntu@public DNS 
```


![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/terminal4.png)

Type yes to connect to your instance server!


Don't know your Public DNS? Go on the Instance Dashboard on AWS and copy it.


![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/terminal5.png)




