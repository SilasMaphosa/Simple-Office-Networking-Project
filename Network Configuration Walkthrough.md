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
- Using the given network 192.168.40.0, all interfaces sould be configured with correct IP addresses, subnet mask and gateways

First I would need to split the network provided (192.168.40.0) into 2 networks. This is done with the use of subnetting.

the best way I remember to subnet is to draw the subnetting table as a guide.

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











