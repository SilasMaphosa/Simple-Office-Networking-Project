# Network Configuration Walkthrough
-------------------------------------
## Step 1 - Network Topology 
When looking at the requirements, I could see that I could  fulfil 4 out of 6 requirements just by  designing  the Network Topology.

Requirements:
- Design a network in Cisco Packet Tracer to connect ACCOUNTS and DELIVERY departments
- Each department should contain at least two PCs.
- An appropriate number of switches and routers should be used in the network.
- All devices in the network should be connected using appropriate cables.

------------------------------------
![Simple office Topology](https://github.com/SilasMaphosa/Simple-Office-Networking-Project/assets/121561502/bf35fb30-9320-45fe-b64b-82b6a8210a4a)
## Step 2 - Subnetting
Next I will complete the Following requirement:
- Using the given network 192.168.40.0, all interfaces should be configured with correct IP addresses, subnet mask and gateways

First I would need to split the network provided (192.168.40.0) into 2 networks. This is done with the use of subnetting.

The best way I remember to subnet is to draw the subnetting table as a guide.

Here is one example that I found from a website that explains subnetting. https://medium.com/networks-security/subnetting-simplified-608aacb5d892

![image](https://github.com/SilasMaphosa/Simple-Office-Networking-Project/assets/121561502/cac5eabe-cafd-4554-bea8-49f90238cd7f)

I created a table based of what is on https://subnetipv4.com/ to show the IP addresses for the 2 networks. this helps me understand what is the first host, last host and broadcast address.

### First Subnet
|Network Info                                       | IP Address                 |
|---------------------------------------------------|----------------------------|
|Network ID                                         | 192.168.40.0               |
| First Host                                        | 192.168.40.1               |
| Last Host                                         | 192.168.40.126             |
| Broadcast Address                                 | 192.168.40.127             |

### Second Subnet
|Network Info                                       | IP Address                 |
|---------------------------------------------------|----------------------------|
|Network ID                                         | 192.168.40.128             |
| First Host                                        | 192.168.40.129             |
| Last Host                                         | 192.168.40.254             |
| Broadcast Address                                 | 192.168.40.255             |

Now that I know this network information, I can use this to assist me when configuring the Router and PCs.

## Step 3 - Router Configuration
After Subnetting has been complete, the next step is to configure all the interfaces with the correct IP address, subnet mask and gateways.

To begin, I will need to activate the router interfaces that are connected to switches in the Accounts and Delivery departments.  

![image](https://github.com/SilasMaphosa/Simple-Office-Networking-Project/assets/121561502/66660fc9-10f3-4c19-9d9b-b6fc22c0b013)

When an interface is shut down, it ceases to function, and no data can be transmitted or received through it. Issuing the "no shutdown" command brings the interface back online.

Next is configuring each router interface with the correct ip address and subnet mask.

![image](https://github.com/SilasMaphosa/Simple-Office-Networking-Project/assets/121561502/cbf0bc20-bffd-4fac-aff7-c224c24a5d28) 

As shown in the screenshot above, the first interface is gig 0/0. I have set the IP address as 192.168.40.1
This will connect to the switch in the accounts department.

![image](https://github.com/SilasMaphosa/Simple-Office-Networking-Project/assets/121561502/02ca61d6-ef53-4472-a367-b789d06e89d2)

The second interface is gig 0/1. I have set the IP address to 192.168.40.129
This will connect to the switch in the delievery department.

After that is complete now its time to confirm that the router interfaces are set up correctly. I will use the 'do show start' command to verify the startup configuration.

![image](https://github.com/SilasMaphosa/Simple-Office-Networking-Project/assets/121561502/24629419-7fec-4e36-b48e-beb537b607e6)

As shown in the above screenshot the start-up configuration hasnt been setup yet. To resolve this issue i used the'copy run start' command so that the router can build the configratuation file.

![image](https://github.com/SilasMaphosa/Simple-Office-Networking-Project/assets/121561502/cc110a98-f146-4015-ac11-b1fb84b4053d)

Now that the start-up configuration is built, I can verify that the configuration is correct.

![image](https://github.com/SilasMaphosa/Simple-Office-Networking-Project/assets/121561502/b242f957-4779-4b05-9f75-c5d7a80ea2d4)

### Step 4 - PC configuration 

After completing the router config it now time to do the PC configuration. For this part, I set up static ip addresses and default gateways for all the PCs. I have only supplied one screenshot as an example as I didnt want to show me repeating the process 4 times. Once this was complete, I fulfiled the following requirement.

- Using the given network 192.168.40.0, all interfaces should be configured with correct IP addresses, subnet mask and gateways

![image](https://github.com/SilasMaphosa/Simple-Office-Networking-Project/assets/121561502/5422a189-685f-471b-be85-0109482341a1)


### Step 5 - Testing.

in this final stage, I worked on completeing the final requirement.

- Test communication between devices in both ACCOUNTS and DELIVERY departments.

to complete this I needed to be able make sure that PCs fromm  the accounts department are able to commincate with PCs in the Delivery department via the router which was set up. the best wau to accomplish this is perform a ping test. 

#### Error that i noticed

When trying to Ping from PC0 to PC2 I got the message 'destination is unreachable'. I then thought I should go through the router configuration to check if it done correctly. That is when i spotted the mistake I made. the IP address was not set up correctly. 

![image](https://github.com/SilasMaphosa/Simple-Office-Networking-Project/assets/121561502/b29ba968-50ad-4a51-ace8-575786a740cd)



![image](https://github.com/SilasMaphosa/Simple-Office-Networking-Project/assets/121561502/9abca69a-4c51-4620-a461-ffdfc079c2d1)
- Correct IP address: 192.168.40.129

I corrected this mistake and rerun the ping test again. The test is now successful and have now completed the final requirement.

![image](https://github.com/SilasMaphosa/Simple-Office-Networking-Project/assets/121561502/f0575286-b0a7-4652-9a55-d96727fcd912)






















