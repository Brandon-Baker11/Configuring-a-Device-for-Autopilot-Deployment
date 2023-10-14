![Windows Autopilot Logo](https://github.com/Brandon-Baker11/Configuring-a-Device-for-Autopilot-Deployment/assets/140644499/8a7a7100-3143-47b8-834a-32bcc03eca8e)
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
![Screenshot1](https://github.com/Brandon-Baker11/Configuring-a-Device-for-Autopilot-Deployment/assets/140644499/7cc3d0cf-fb2d-4aec-8259-270f295de85a)


When you get to this page, click ***Create Profile*** and select ***Windows PC*** in the drop down menu.
![Screenshot2](https://github.com/Brandon-Baker11/Configuring-a-Device-for-Autopilot-Deployment/assets/140644499/593b9e3f-aac0-443a-b315-b09e70787813)


On the ***Create Profile-Basics*** page, enter a naming convention and description that works for you. And select ***Yes*** for the ***Convert all targeted devices to Autopilot***.
Click ***Next***
![Screenshot3](https://github.com/Brandon-Baker11/Configuring-a-Device-for-Autopilot-Deployment/assets/140644499/2bc43cc6-3826-49da-9f2a-93b850537f10)


On the *** Out-of-Box-Experience*** tab click ***Language (Region)*** and select the language and region that applies to you.
Click ***Next***
![Screenshot4](https://github.com/Brandon-Baker11/Configuring-a-Device-for-Autopilot-Deployment/assets/140644499/48cbbf90-466c-4183-bf0c-2f71bd68e303)


Next, click the ***Apply device name template*** and type ***Yourprefix%RAND:4***. This will be the name that's assigned to your Autopilot deployment device when the setup is complete. So in my case, my computer's new name will be ***HLab*** with four random numbers after it.
Click ***Next***
![Screenshot5](https://github.com/Brandon-Baker11/Configuring-a-Device-for-Autopilot-Deployment/assets/140644499/6853ea27-ec95-4663-825d-c246856e6856)


In the ***Assignments*** tab select ***Add all devices*** under the ***Included Groups*** section.
Click ***Next***
![Screenshot6](https://github.com/Brandon-Baker11/Configuring-a-Device-for-Autopilot-Deployment/assets/140644499/5e3cfad1-ab4b-416d-b76d-1d7e84f69c29)


On the ***Review + Create*** tab click ***Create***.
![Screenshot7](https://github.com/Brandon-Baker11/Configuring-a-Device-for-Autopilot-Deployment/assets/140644499/06a1418c-79c5-4c5f-a1ca-a808a04abea7)


Now that we've created the Autopilot profile for our device, we will import the hardware ID used for the Autopilot deployment. In the search bar in the task bar, type ***Access work or school*** and select it from the best match selection.
![Screenshot8](https://github.com/Brandon-Baker11/Configuring-a-Device-for-Autopilot-Deployment/assets/140644499/b8a97d2b-f1fc-46cd-b669-4a2b1a8a1c91)


On the ***Access work or school*** window click ***Export under the ***Related settings*** section. When you click export, there won't be a notification telling you it was successful.
![Screenshot9](https://github.com/Brandon-Baker11/Configuring-a-Device-for-Autopilot-Deployment/assets/140644499/70858cd8-0649-4c57-b757-2377c8ce5934)


Open the file explorer from the task bar and type this in to the task bar: ***C:\Users\Public\Public Documents\MDMDiagnostics***
![Screenshot10](https://github.com/Brandon-Baker11/Configuring-a-Device-for-Autopilot-Deployment/assets/140644499/6f4d4e84-cfbf-4922-8017-32a61f5a94fd)


Open the ***MDMDiagReport*** cabinet file and find the ***DeviceHash*** csv file. Right-click the file and select ***Copy*** and save it to your ***Documents*** folder to make it easier to find when we import it to Intune.
![Screenshot11](https://github.com/Brandon-Baker11/Configuring-a-Device-for-Autopilot-Deployment/assets/140644499/b1fbcb0d-1978-4053-a588-3472df05a468)


We will now restore our Microsoft Edge session that had the ***Intune Admin Center*** open and go to ***Devices, Windows, Windows Enrollment*** and scroll down to the ***Windows Autopilot Deployment Program*** section and click ***Devices***.
![Screenshot12](https://github.com/Brandon-Baker11/Configuring-a-Device-for-Autopilot-Deployment/assets/140644499/c699d358-7397-4b32-8524-d69fe9547d3d)


Click ***import*** at the top of the page and select the folder icon in the fly-out window. Now we can go to your ***Documents*** folder and select the csv file that we pasted there earlier.
Then click ***Import*** once you've selected the csv file. This can take up to **15 min** to complete so don't move on until the import is complete.
![Screenshot13](https://github.com/Brandon-Baker11/Configuring-a-Device-for-Autopilot-Deployment/assets/140644499/b07ad635-e500-406a-9ffb-844067d807f7)


Next, we are going to completely reset our computer to bring us back to the Out of Box Experience; as if we were freshly installing the OS. Right-click the Windows charm in the task bar and select ***Settings***.
![Screenshot14](https://github.com/Brandon-Baker11/Configuring-a-Device-for-Autopilot-Deployment/assets/140644499/7ae51e03-a1f4-40aa-a1a5-4e3153274a99)


From ***Settings*** click ***System***, and scroll down to ***Recovery***.
![Screenshot15](https://github.com/Brandon-Baker11/Configuring-a-Device-for-Autopilot-Deployment/assets/140644499/44a21d91-e491-4296-9d8d-a62d7fec3412)


Under ***Recovery Options*** click ***Reset PC***, then click ***Remove everything***.
![Screenshot16](https://github.com/Brandon-Baker11/Configuring-a-Device-for-Autopilot-Deployment/assets/140644499/aca78973-89b3-4355-ac43-f62d1d4e79a0)


Click ***Local Reinstall*** and click ***Next***
![Screenshot17](https://github.com/Brandon-Baker11/Configuring-a-Device-for-Autopilot-Deployment/assets/140644499/251ff396-712d-4196-9ddb-de1bdd595480)








































































































































































