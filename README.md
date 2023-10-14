![Windows Autopilot Logo](https://github.com/Brandon-Baker11/Configuring-a-Device-for-Autopilot-Deployment/assets/140644499/872f34ec-7a07-45fd-b0b6-eb3c8ee5e7dc)
# Configuring-a-Device-for-Autopilot-Deployment
This tutorial will walk you through the process of configuring a device for a Windows Autopilot Deployment in a lab environment.

## Environments and Technologies Used
- OracleVM VirtualBox

## Operating Systems Used
- Windows 11 (22H2)

## Deployment and Configuration Steps
In this lab, we will go through the process of setting up a Windows desktop to be deployed using Windows Autopilot. These steps will include:

- Create a profile for an Autopilot deployment using Intune.
- Importing the device's hardware ID for the deployment.
- Deploying the device using Autopilot.


What we will do first is sign in to the Intune Admin Center using a Microsoft 365 account. You will then click ***Devices***, select ***Windows*** inside Devices, then select ***Windows enrollment***, and then select ***Deployment Profiles*** in the ***Windows Autopilot Deployment Program*** section. You will arrive at this page:
![Screenshot1](https://github.com/Brandon-Baker11/Configuring-a-Device-for-Autopilot-Deployment/assets/140644499/b3881266-1ea0-434c-806c-06a09e58d713)


When you get to this page, click ***Create Profile*** and select ***Windows PC*** in the drop down menu.
![Screenshot2](https://github.com/Brandon-Baker11/Configuring-a-Device-for-Autopilot-Deployment/assets/140644499/eef2156a-f514-4936-ac1e-7ba9283cfb2e)


On the ***Create Profile-Basics*** page, enter a naming convention and description that works for you. And select ***Yes*** for the ***Convert all targeted devices to Autopilot***.
Click ***Next***
![Screenshot3](https://github.com/Brandon-Baker11/Configuring-a-Device-for-Autopilot-Deployment/assets/140644499/ef5afdd4-f24a-4d83-a64d-b20cb320df0c)


On the *** Out-of-Box-Experience*** tab click ***Language (Region)*** and select the language and region that applies to you.
Click ***Next***
![Screenshot4](https://github.com/Brandon-Baker11/Configuring-a-Device-for-Autopilot-Deployment/assets/140644499/1beea63d-0191-4d5c-ac78-0bf65725c042)


Next, click the ***Apply device name template*** and type ***Yourprefix%RAND:4***. This will be the name that's assigned to your Autopilot deployment device when the setup is complete. So in my case, my computer's new name will be ***HLab*** with four random numbers after it.
Click ***Next***
![Screenshot5](https://github.com/Brandon-Baker11/Configuring-a-Device-for-Autopilot-Deployment/assets/140644499/660c0b13-26bc-4196-8461-bb89bb310355)


In the ***Assignments*** tab select ***Add all devices*** under the ***Included Groups*** section.
Click ***Next***
![Screenshot6](https://github.com/Brandon-Baker11/Configuring-a-Device-for-Autopilot-Deployment/assets/140644499/004abcc6-cb3a-44e9-a804-974fb93d4dff)


On the ***Review + Create*** tab click ***Create***.
![Screenshot7](https://github.com/Brandon-Baker11/Configuring-a-Device-for-Autopilot-Deployment/assets/140644499/4983c6fc-9354-4914-8b33-1bb3e2166fd1)


Now that we've created the Autopilot profile for our device, we will import the hardware ID used for the Autopilot deployment. In the search bar in the task bar, type ***Access work or school*** and select it from the best match selection.
![Screenshot8](https://github.com/Brandon-Baker11/Configuring-a-Device-for-Autopilot-Deployment/assets/140644499/24f4aadb-e127-4d75-b49c-0ebc93c1ad8f)


On the ***Access work or school*** window click ***Export under the ***Related settings*** section. When you click export, there won't be a notification telling you it was successful.
![Screenshot9](https://github.com/Brandon-Baker11/Configuring-a-Device-for-Autopilot-Deployment/assets/140644499/772f22c6-bc12-4679-8a28-a0b04073ee98)


Open the file explorer from the task bar and type this in to the task bar: ***C:\Users\Public\Public Documents\MDMDiagnostics***
![Screenshot10](https://github.com/Brandon-Baker11/Configuring-a-Device-for-Autopilot-Deployment/assets/140644499/c522526a-fb94-4ab5-ac46-d76dc601e218)


Open the ***MDMDiagReport*** cabinet file and find the ***DeviceHash*** csv file. Right-click the file and select ***Copy*** and save it to your ***Documents*** folder to make it easier to find when we import it to Intune.
![Screenshot11](https://github.com/Brandon-Baker11/Configuring-a-Device-for-Autopilot-Deployment/assets/140644499/1c864e89-2668-43f8-9c97-b85e3694713a)


We will now restore our Microsoft Edge session that had the ***Intune Admin Center*** open and go to ***Devices, Windows, Windows Enrollment*** and scroll down to the ***Windows Autopilot Deployment Program*** section and click ***Devices***.
![Screenshot12](https://github.com/Brandon-Baker11/Configuring-a-Device-for-Autopilot-Deployment/assets/140644499/69bbbc02-dad9-4d27-b751-80ad52db2a35)


Click ***import*** at the top of the page and select the folder icon in the fly-out window. Now we can go to your ***Documents*** folder and select the csv file that we pasted there earlier.
Then click ***Import*** once you've selected the csv file. This can take up to **15 min** to complete so don't move on until the import is complete.
![Screenshot13](https://github.com/Brandon-Baker11/Configuring-a-Device-for-Autopilot-Deployment/assets/140644499/bc42da81-ca46-47ff-90f2-de6daab7749d)


Next, we are going to completely reset our computer to bring us back to the Out of Box Experience; as if we were freshly installing the OS. Right-click the Windows charm in the task bar and select ***Settings***.
![Screenshot14](https://github.com/Brandon-Baker11/Configuring-a-Device-for-Autopilot-Deployment/assets/140644499/8620de48-2e4f-40ed-8e9e-df19c484bf9b)


From ***Settings*** click ***System***, and scroll down to ***Recovery***.
![Screenshot15](https://github.com/Brandon-Baker11/Configuring-a-Device-for-Autopilot-Deployment/assets/140644499/8a19cbec-f54e-4898-865a-4dfc749f3f7a)


Under ***Recovery Options*** click ***Reset PC***, then click ***Remove everything***.
![Screenshot16](https://github.com/Brandon-Baker11/Configuring-a-Device-for-Autopilot-Deployment/assets/140644499/c7b49b3a-5a19-46a1-8446-513ce61e66db)


Click ***Local Reinstall*** and click ***Next*** until you get the option to select ***Reset*** and reset your system.
![Screenshot17](https://github.com/Brandon-Baker11/Configuring-a-Device-for-Autopilot-Deployment/assets/140644499/1649fb48-46b4-42f8-b1c0-05c81d6badf0)


Once your computer has been reset, you should arrive at the screen below. Enter in the credentials for your Microsoft 365 account and click ***Sign in***
![Screenshot18](https://github.com/Brandon-Baker11/Configuring-a-Device-for-Autopilot-Deployment/assets/140644499/65f2695c-7bef-4d5e-9558-c1fdd90ed097)


We are going to skip implementing Windows Hello for now. So, on the ***Use Windows Hello with your account*** screen, click ***Ok***. Then on the ***More information required*** pop-up click ***Next*** and close the window that was behind the ***More information required*** window. Then click ***Skip for now***
![Screenshot20](https://github.com/Brandon-Baker11/Configuring-a-Device-for-Autopilot-Deployment/assets/140644499/46aa06ff-5282-459a-ac7f-10251708a009)


Now that our system has logged in we can verify that the naming convention that we chose to include in the Autopilot deployment process works correctly. Right-click the Windows charm in the task bar and select ***Windows PowerShell (Admin)***.
Click ***Yes*** on the UAC pop-up.
![Screenshot21](https://github.com/Brandon-Baker11/Configuring-a-Device-for-Autopilot-Deployment/assets/140644499/dffedb42-1bc3-45ec-9156-3e85771c4eaa)


Once you're in PowerShell, type the following command:
`hostname`
Press ***Enter***
![Screenshot22](https://github.com/Brandon-Baker11/Configuring-a-Device-for-Autopilot-Deployment/assets/140644499/069cc718-e51b-43ff-ac19-4d773d343c62)


And if you see your naming convention returned after the command, you have successfully deployed this device using Autopilot!
![Screenshot23](https://github.com/Brandon-Baker11/Configuring-a-Device-for-Autopilot-Deployment/assets/140644499/7eb59fe9-1814-4646-87a2-fbd7e3472b60)

























































































































































