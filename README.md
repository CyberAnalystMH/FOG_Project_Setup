WORK IN PROGRESS

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

**Annotations:** First we setup our router, could either virtual or physical. There's a lot of ways to set-up Pfsense or similar, consult the manual or a video tutorial. After you have your router, ensure to assign it an IP address range. After so, connect your devices which in this cause we have "LinuxIsCoolCapture" and "LinuxIsCoolDepoly" hence the name one machine will be the capture or the machine that will be cloned and then deploy or the machine that will get the clone system. Ensure those machines have a static IP address to ensure smooth network booting, you can run into problems if the DHCP changes the IP address of the devices or any reasons. 
