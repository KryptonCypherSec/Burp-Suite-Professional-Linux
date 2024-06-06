# Burp-Suite-Professional-Linux
![photo_2024-06-06_12-51-37](https://github.com/KryptonCypherSec/Burp-Suite-Professional-Linux/assets/171511773/834de21c-1451-4983-9bc6-cd1045423206)    

The important thing which exists within the professional version and you maybe know it, is the Collaborator tool and another features like that which you cannot use them in Community Edition. So in the repository I'll show you how to install Burp Suite Professional on your unix based operating system.   

**DISCLAIMER:  
I'm not responsible for any OS problems or Security issues that may occur or any Illegal usage of this program. So please read carefully and do it step by step at your own risk.**   

**Flow:**  

Let me explain the work-flow first. We will donwload the official version of Burp Suite Professional and then we will use a license generator to generate access to a license for our program. I've scanned files with **ClamAV** and found these files safe. So you can do it with your own malware scanner or anything else you want ;)

Let's get started:  

Before we get started with main steps,I'm kindly ask to:  
*  Uninstall your Community Edition of Burp Suite using these commands:  
```
sudo apt-get remove burpsuite
sudo apt-get autoremove
sudo apt update
```  
*  Run your terminal as Root or only type `sudo -i` or `sudo su`, to prevent encountering errors.  

**First Step**
*  **1**.The first thing that you should do is to clone this repository in a directory like `/home/user/Desktop` or anywhere that you want.  

*  **2**.Then you should download the Burp Suite professional `.jar` file from official site: [Burp Suite Professional](https://portswigger.net/burp/releases).  

*  **NOTE**: You should download the `.jar` file. (version doesn't matter) then put the `.jar` file in the directory that you've cloned the repository.  
![photo_2024-06-06_13-04-20](https://github.com/KryptonCypherSec/Burp-Suite-Professional-Linux/assets/171511773/af82dff6-aa40-4d67-9edc-f25702d88432)  

*  I prefered the [Burp Suite Pro v2024.4.4](https://portswigger.net/burp/releases/professional-community-2024-4-4) stable version, so I'll describe based on this version. But you should note that you need to change the version of the file if you downloaded another version!

*  **3**.After that you should make a directory with this command:  
  ```mkdir /etc/opt/burpsuite```

*  **4**.Then you should head to the directory that you cloned the repository and copy the `BurpLoaderKeygen.jar` and program file `burpsuite_pro_v2024.4.4.jar` and the image `burp.png` to `/etc/opt/burpsuite`. After that you should change your directory to `/etc/opt/burpsuite` using `cd`.  

*  **5**.Then you should make the `.jar` files, executable with these commands:

  ```chmod +x BurpLoaderKeygen.jar```  
  ```chmod +x burpsuite_pro_v2024.4.4.jar```     

*  **6**.Then run the `BurpLoaderKeygen.jar` with this command:  
  ```java -jar BurpLoaderKeygen.jar```  

If you have done all of them right, you will see a screen like this:  

![photo_2024-06-06_13-46-00](https://github.com/KryptonCypherSec/Burp-Suite-Professional-Linux/assets/171511773/fefb02db-825e-4bdd-b51a-3e6277c8ae63)  

I'll explain step by step what you should do right now!  

*  **7**.First of all copy whole of the text of `Loader Commnad` and paste it somewhere like notepad. Then hit that run button:  

![photo_2024-06-06_13-57-06](https://github.com/KryptonCypherSec/Burp-Suite-Professional-Linux/assets/171511773/9c3b0343-46ce-4c77-adb3-7e048b41226a)  
 

*  After doing that you will face that Burp Suite is running and after that it wants the license key.  

![burpsuite](https://github.com/KryptonCypherSec/Burp-Suite-Professional-Linux/assets/171511773/214dc4aa-105c-4f04-a7d3-6501756c0dd0)  

*  **8**.So copy the license from this page and paste it in the Burp Suite and hit the **Next** button:  

![photo_2024-06-06_14-00-32](https://github.com/KryptonCypherSec/Burp-Suite-Professional-Linux/assets/171511773/620d8d97-8712-43f3-a690-a1e020c424af)  

*  After that you will face an activation page like this:  

<img width="520" alt="mac-installer-7" src="https://github.com/KryptonCypherSec/Burp-Suite-Professional-Linux/assets/171511773/5a5cfd83-7afe-4cbd-9214-8e6b2af593d2">  

*  **9**.Hit that **Manual Activation** button and copy the Activation Request.  

*  **10**.Then paste it here:

![photo_2024-06-06_14-10-56](https://github.com/KryptonCypherSec/Burp-Suite-Professional-Linux/assets/171511773/a4b50906-8320-4721-839b-006150193ded)  

*  After that copy the **Activation Response** and paste it in the Burp Suite and hit **Next** and then hit **Finish** button.Congratulations! you have done it!  
  
**Second Step**

Now we should run it but how?   

*  **11**.If you go to your applications menu, you can't see Burp Suite, and if you try to search it you connot find that!. So what we can do?  
Do you remember that code that we kept it from 7th stage? We should go and edit that. It has some `"` that we should remove them. Please be careful and don't remove spaces.  

*  **12**.After you cleared the run command, you can test it by going to terminal and paste it. Please note that if you have done whole of the process in a right way, you will see that Burp Suite professional start working. And if you done it wrong, you will face the first page that wants you a license again! So if you encounter this situation, please go back to the first step and do the whole process again.

*  **13**.So if you passed the last step, it's time to make a shortcut for our Burp. To do that we will make a desktop file for it using this command:  

`nano /usr/share/applications/burpsuite.desktop`  

*  **14**.Then paste this code inside of it:  

```
[Desktop Entry]
Version=1.0
Type=Application
Name=Burp Suite
Comment=Burp Suite Professional
Exec=[YOUR_COPIED_COMMAND_FROM_NOTEPAD]
Icon=/etc/opt/burpsuite/burp.png
Terminal=false
Categories=Development;Security;
```

*  **15**.Note that instead of `[YOUR_COPIED_COMMAND_FROM_NOTEPAD]` in `Exec` in upper code, you sude paste the execute command that you have made in 11th step.

*  **16**.Now press `Ctrl+S` to save the file and then `Ctrl+X` to close the file.  

*  **17**.If you did everything well, you can double click on Burp Suite Icon which exists in your applications menu, and after that you will get into the Burp Suite menu. Please note that if you cannot see anything or you keep seeing the license page of Burp Suite, it means that you have made a mistake and you should do the whole process again! In my opinion somewhere between 13th and 16th step.


**After installing** the program you may need to re-certify your browser to prevent or solve some common errors.To do that you can easily go to [Burp Certificate Page](https://burpsuite), and at top right of the screen hit that **CA Certificate** and then download the `.der` file and re-certify your browser. Please note that in Chrome and Brave browser you need to chooze the certificate from **Settings>Privacy and security>Manage certificates>Authoroties>Import** and in Firefox browser **Settings>Privacy & Security>Certificates>View Certificates>Import**.  

Please note that I've used this program for couple of weeks, and I didn't see any issues or like that.If you encounter any issues this is your fault in licensing, installing or certifying your browser.
Now the program is licensed on your system. Go and enjoy learning :)







