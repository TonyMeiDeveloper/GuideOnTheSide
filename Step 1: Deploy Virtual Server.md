#Step 1: Deploy Virtual Server


I started from scratch. I have no server so I will sign up for AWS or Amazon Web Services which provides cloud servers.  
Go to https://aws.amazon.com. To sign up, you will need an email address and credit card information. Don't worry. You only get charged if free trial is all used or if you add more services. Be sure to check out pricing at https://aws.amazon.com/pricing/services/. 


##Launching a Server in AWS


![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/AWS.png)


After you sign up, go to the top and Click My Account -> AWS Management Console. You will be greeted with a dashboard of Amazon Web Services.


![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/Dashboard1.png)


![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/Dashboard2.png)


Once you click on EC2, you will be greeted with a dashboard. At first glance, it will seem overwhelming, but we will go over only the configurations you need to deploy Guide on the Side or any web applications once you have the server set up.    


![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/CreateInstance1.png)   



Right in the middle of the dashboard, you will see a big blue button to launch instance. Click on it. From my understanding, an Instance is a virtual server. 


![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/CreateInstance2.png)


##Choosing Configurations for your Instance Server

###First Configuration
The first thing you see is Choosing an Amazon Machine Image or Operating System for your server. For my case, I will choose Ubuntu Server 14.04. Also keep in mind which are covered in the free trial. 


![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/config1.png)


###Second Configuration
Second configuration is specifying the specs or hardware of the virtual machine you want. You can choose what kind of CPUs, how much memory, etc, for your machine. Since, I am on the free tier, I will choose the t2.micro type.  


![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/config2.png)


###Third Configuration
Third configuration is setting how many instance you want as well as other settings like VPC, IAM, etc. For simplicity, I'll leave this page as is and don't change anything.     


![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/config3.png)


###Fourth Configuration 
Fourth configuartion is adding more storage to your virtual server, but keep in mind that there is a limit on storage for Free Tier customers. 


![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/config4.png)


###Fifth Configuration
Fifth configuration is about tagging instances and resources. I believe it is used for better searching and navigation. For my case, I don't really need it so I left it alone. 


![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/config5.png)


###Sixth Configuration
Sixth Configuration is where you create a new security group. Security groups are essentially a set of rules that control incoming and outgoing traffic for your instance. You can allow or disallow SSH, POP3, DNS, and others on your virtual server.      

For this case, we will need SSH to connect to the virtual server to install a variety of tools and deploy Guide on the Side and HTTP so that the web application can be display on internet browsers like Google Chrome, Safari, and Internet Explorer, etc. 

Do this: 
![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/config6.png)


Then do this: 
![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/config6.5.png)


###Seventh Configuration
Seventh Configuration is review all the settings and configurations you did for your virtual server. You can make last minute changes if you want.


![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/config7.png)


###Obtaining key and SSH
After you are done with the Seventh Configuartion, you will be greeted with an option to create a new key pair to connect to your instance or virtual machine. 

Choose Create a new Key Pair and Choose the name of your key and download it. This .pem file or private key will be needed to SSH to your vitual server.  

![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/config7.5.png)


Click launch and your instance will be launched. You can find your instance and its status on the dashboard. 


![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/instancedashboard.png)


Let's begin connecting to our instance server. On the dashboard:
![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/instancedashboard2.png)


Once you click on Connect, you will see this, which are instructions on how to connect via SSH. If you are on Linux or Mac, follow the instructions. If you are on Windows, you will have to use Putty. 


![alt tag](https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/GuidePictures/connect.png)

##SSH via Putty if you are Windows 
<a href="https://github.com/TonyMeiDeveloper/GuideOnTheSide/blob/master/MoreResources/PuttySSH.md" target="_blank">example</a>

##SSH via Terminal if you are on Linux or Mac



##Moving on after you connect to your instance server
Let's SSH to connect to our instance server. I will be using a variety of Terminal Commands. Here are some common ones you should know before moving on:

```
ls
cd 
cd ..
vim
sudo
```





