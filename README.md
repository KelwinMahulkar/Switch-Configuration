# Switch-Configuration
This project shows simple configuration of a switch.

The following image displays the topology of the network.
![topology](https://user-images.githubusercontent.com/69259617/116957763-ac29e300-ac66-11eb-91ee-ff4a86bdc426.JPG) 

The configuration includes assigning hostname, IPv4 address, assigning passwords to switch access and console/vty lines and checking connectivity.

First, cable the devices and start the terminal session in PC-A. Enter **enable** command in order to enter Privileged EXEC mode. 
Once there, enter the command **show run**. It will display all the saved configurations which are done previously. 
Enter the global configuration mode by entering **config t** command.
Here we can assign IP addresses to interfaces, assign/change hostname and many other such functions. 
To assign a hostname to the switch S1 - **hostname S1**. Now the switch has been assigned the hostname of S1.

Then assign passwords to line console and vty lines:
  #line con 0
  #password cisco
  #login
  #exit
 For vty lines:
  #line vty 0 4
  #password cisco
  #login
  #exit
The login command is issued to prompt for login while accessing.
Assigning IP address:
  #interface vlan 1
  #ip address 192.168.1.2 255.255.255.0
  #no shut
  #exit
The **no shutdown** command is issued to keep the interface up. 

The following is the image of the configure passwords and assigned IPv4 addresses. 
![rc_IP Pass](https://user-images.githubusercontent.com/69259617/116973735-f7ee8380-ac8a-11eb-9331-3eff5dcc2e26.JPG)

The following is an image of the interfaces. Only interfaces FastEthernet 0/6 and VLAN 1 are up because the PC is connected to the Switch through F0/6 and we have assigned IP address to the VLAN 1 interface and issued no shutdown command.
----------------------------------------------------

Finally, the connectivity test. First ping the PC itself. Then ping the Switch using ping command. 
The output of the ping command is shown below.
------------------------------------------------------------------------
