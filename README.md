# Summary
One of my first project was implementing FOG Project, which is "A free open-source network computer cloning and management solution" It's a really neat project that let's you customize a Operating System of any kind and deploy exact clones of it to as many machines needed, the only thing needed for deployment is the FOG dashboard and the computers set to "Network Booting". This project was done about two years ago, not all the steps have screenshots, for detailed instructions on how to deploy and to Learn more about The FOG Project visit:

**This Website:** https://fogproject.org/ 
# Setup

**Needed Equipment & Tools*

**Hardware Based:**
- **Laptops:** 2X or more
- **Network:** 1X Router and a large 1X Switch 
- **Ethernet Cables:** Depending on how many laptops

**Virtual Based:**
- **PC or Laptop:** 1X
- **Software:** Virtual Box or similar

**Note:** I don't have access to more then one physical laptop/PC, in this case we're going to virtulize it.
# Scenario  

You're an IT employee at a newly built College and your boss asks you to install and deploy 100 Hannah Montana Linux on the school's computer stations. You're given the equipment, a router and a large switch with many Ethernet cables and of course the 100 computers. 

**Note:** We're going to be deploying a single clone but the concept is the same if we were to actually deploy 100 clones of the same system. 

# Walk-Through and Annotations  

<img width="1447" height="442" alt="image" src="https://github.com/user-attachments/assets/f94147dd-1a49-451e-869e-405aea718973" />

**Annotations:** First we setup our router, could either virtual or physical. There's a lot of ways to set-up Pfsense or similar, consult the manual or a video tutorial. After you have your router, ensure to assign it an IP address range. After so, connect your devices which in this cause we have "LinuxIsCoolCapture" and "LinuxIsCoolDepoly" hence the name one machine will be the capture or the machine that will be cloned and then deploy or the machine that will get the clone system. Ensure those machines have a static IP address to ensure smooth network booting, you can run into problems if the DHCP changes the IP address of the devices or any reasons.

**Additional Annotations:** Like most web based service, we need a system that the web server aspect of it to be deployed or ran on that isn't the capture or the deploy VM. I imaged Ubuntu 22 on a VM and labeled it as "FOGMASTER" and installed the script that was provided by The Fog Project. 

<img width="1221" height="792" alt="image" src="https://github.com/user-attachments/assets/3d519dfc-2540-4521-a921-6d285bd5113d" />

**Annotations:** On the capture machine, we're going to deploy FOG Management, which is a nice GUI to see our machines and some other statistics that we may need. 

**Additional Annotations:** Before you do anything else, install the OS on the capture machine and create user and everything, like you would normally and reboot into this screen

<img width="1548" height="622" alt="image" src="https://github.com/user-attachments/assets/1109ff4d-9846-48cc-8ba6-1efccd01de73" />

**Annotations:** Ensure those machines are connected to the internal network, in this case, the Pfsense and also ensure the BIOS of those machines are selected to Boot into Network and not a hard drive. First, we're going to work with the capture machine to capture our OS, once you boot into the FOG Project Boot menu, ensure to select "Perform Full Most Registration and Inventory". Also be aware, similar to the Linux Boot, you only have 3 seconds to act in selecting your menu. 

<img width="861" height="521" alt="image" src="https://github.com/user-attachments/assets/5b731623-f2f0-4f9a-8676-976196576554" />

**Annotations:** Once you boot in to capture machine, it will load FOG ASCII art and asks you to enter hostname of the machine. You can choose any hostname, doesn't have to be the same hostname as your machine, it's just for FOG to differentiate different machine names. 

<img width="468" height="21" alt="image" src="https://github.com/user-attachments/assets/4025a9f2-2123-476c-bf6a-e9d3b7258e4f" />


**Annotations:** In this case, we're gonna name it something silly, such as "LinuxIsCool"


<img width="731" height="313" alt="image" src="https://github.com/user-attachments/assets/144ad7d9-0125-419f-8c23-101e91e3623c" />



**Annotations:** It's going to ask you other questions, say No to all of them. If you're curious what they're, consult FOG Documentation and then at the end it's gonna ask you if you want to deploy now, ensure that you say NO because it makes more sense to deploy from the FOG Management and not the GUI, as you can control more machines on the GUI. 


<img width="1115" height="540" alt="image" src="https://github.com/user-attachments/assets/1aa1bae9-7027-4397-8885-7e2650e2a538" />


**Annotations:** Speaking of which, we're going to get back to the Management and click on the computer icon and then ensure our "LinuxIsCool" is showing up by click on "List All Hosts" . We're deploying Linux but the Management shows we may be deploying a Windows, please ignore that. 


<img width="1453" height="900" alt="image" src="https://github.com/user-attachments/assets/fe3ffd05-edc7-49f6-8178-36cb3a5465f3" />

**Annotations:** Click on "Create New Image" then name the image, give it a description if needed. Change OS to "Linux" or whatever system your trying to deploy. Select "Single Disk - Re-sizable - (1)" and keep everything else the same. 


<img width="1115" height="540" alt="image" src="https://github.com/user-attachments/assets/075a86ed-d207-4bed-9ff9-13cf6f67d07a" />


 
**Annotations:** Speaking of which, we're going to get back to the Management and click on the computer icon and then ensure our "LinuxIsCool" is showing up by click on "List All Hosts" . We're deploying Linux but the Management shows we may be deploying a Windows, please ignore that. 

<img width="981" height="810" alt="image" src="https://github.com/user-attachments/assets/3c3e6e7b-87c2-4b84-9591-d432e8bdcf13" />

**Annotations:** The Management should also detect the OS that we're using, in this case, it's "Hannah Montana OS". Then we're gonna click on the "LinuxIsCool" then choose the "Host Image" then "Update".



<img width="414" height="487" alt="image" src="https://github.com/user-attachments/assets/090ee6bd-aafa-4cac-a1ca-5e41991fa327" />


**Annotations:** In the Fog Management, under the tabs their are sub tabs and one of them is "Basic Tasks" which shows that we can Capture and Deploy. Since we're not done with capturing yet, we're gonna click "Capture" to capture our current image. 


<img width="989" height="294" alt="image" src="https://github.com/user-attachments/assets/ac283154-c7f8-41ac-a3a2-ee1686ef9a04" />



**Annotations:** We're creating a capture task, ensure that "Wake on LAN?" and "Schedule instant" is checked then, simply press "Task:.


<img width="1003" height="552" alt="image" src="https://github.com/user-attachments/assets/51b70858-c05a-473a-a20c-9344f6371001" />

**Annotations:** This screenshot simply shows the progress of our capture task and you can cancel the task for any reasons. 


<img width="727" height="409" alt="image" src="https://github.com/user-attachments/assets/05ee90fa-b423-4f47-9aa1-48dbef77d4d5" />

**Annotations:** On the system, it should show this loading screen, showing that it's being actively captured, wait until it's done. After it's done, we're finally done capturing. However, the next thing is to boot up the machine you want to deploy the capture on. 


<img width="743" height="411" alt="image" src="https://github.com/user-attachments/assets/255c19a8-04fc-4213-9f5b-632edb34aece" />


**Annotations:** Now we run the same exact steps to get this menu again and call it something else, which in this instance it's "LinuxIsCool02" to keep it simple, we're cloning or deploying this time so, the steps after this menu is a little different. 

<img width="1009" height="337" alt="image" src="https://github.com/user-attachments/assets/bd9062a4-9127-4e78-924b-24863c46f43b" />

**Annotations:** Like the other system, it should show on our Management and then click on it, then choose the "Host Image" that we created which is that other initial system we've captured. 

<img width="260" height="298" alt="image" src="https://github.com/user-attachments/assets/630654e6-d09c-4b9d-8e1b-de995b4847b6" />


**Annotations:** Going back to the menu above, select "**Deploy**" instead of "Capture"


<img width="719" height="399" alt="image" src="https://github.com/user-attachments/assets/60af4b48-f756-4311-a21f-0084c9e50db0" />

**Annotations:** On the deploy machine, we should see a screen similar to the capture screen. 

<img width="985" height="108" alt="image" src="https://github.com/user-attachments/assets/50042d8a-1aed-4bf0-a510-4b18370112de" />

**Annotations:** We also get a loading screen on the Management interface, which is sort of neat


<img width="531" height="170" alt="image" src="https://github.com/user-attachments/assets/db7b5753-9112-4f7c-83ac-5c540481149c" />


**Annotations:** After the loading is done, it should reboot the system and into your new really cool Hannah Montana OS:



<img width="1005" height="766" alt="image" src="https://github.com/user-attachments/assets/e3006b24-0b02-41c0-9ab9-619b851c3831" />





# Conclusion
I really enjoyed the comprehensiveness of this really cool open source project. Their are other tools similar to FOG, but FOG makes the process fun and doable and doesn't cost any money. You may benefit from this breakdown if you or your company needs an efficient network imaging solution. 




