# Point-to-Point Single-Area OSPFv2 Configuration

In this report I configure Single-Area OSPFv2 and I do the following.:

- Configure Router IDs
- Configure Networks for OSPF Routing
- Configure Passive Interfaces 
- Verify OSPF configuration


## Configure Router IDs

To configure router IDs you must use following commands in the configuration mode. 

"router ospf process-id" - this command starts OSPFv2 routing process in Cisco devices. 
Router ID is a 32-bit value represented as an IPv4 address. It can be assigned automatically by router.

Router which has OSPF enabled with ID does the following 
- Participate in the synchronization of OSPF databases
- Participate in the election of the designated router (DR) 

I configured process id of 10 for all of the routers in the example. After I had this done I configured the following IDs for each router:
- R1 1.1.1.1
- R2 2.2.2.2
- R3 3.3.3.3

router-id ridd - command assigns the router ID 

## Configure networks for OSPF Routing

After enabling OSPFv2 and their IDs. I started configuring networks for them. 

 As we can see we have 3 routers in the same network and each have 3 interfaces connected to them. So I have 3 statemes per router. (3 interfaces connected with end devices)

<img width="688" height="487" alt="image" src="https://github.com/user-attachments/assets/87576256-d764-48be-a8f5-3621f3c28cfe" />

Using the network commmand I can specify which interaces belong to a point-to-point network. I can also use ip ospf command, but in this example it will not be used. 

 network network-address wildcard-mask area area-id
 - area-id refers to the ospf area.
 - network command must be configured with the same area-id on all routers, which is in this case 0. 

# Counting wilcard masks

Wildcard mask is typically inverse of the subnetmask and the easiest way to calculte it is to subtract the network subnet mask from 255.255.255.255. 

R1 Has the following values:
-G0/0/0 192.168.10.1 /24
-S0/1/0 10.1.1.1 /30
-S0/1/1 10.1.1.5 /30

Math for each interface is the following

G0/0/0 255 - 0 = 0, Wildcard is 0.0.0.255

S0/1/0 255 - 252 = 3, Wildcard is 0.0.0.3

S0/1/1 255 - 252 = 3, Wildcard is 0.0.0.3 

I did the same calculations for R2 and R3 the results were identical. 

Now we can configure networks and wildcard for OSPF Routing using the following command. 

 network network-address wildcard-mask area area-id 

 The process looks like this:
 <img width="698" height="710" alt="image" src="https://github.com/user-attachments/assets/ba1f3a07-d421-4bdf-a4da-065f7b2b3dab" />

Example from R3:
<img width="663" height="265" alt="image" src="https://github.com/user-attachments/assets/8e7b1fc5-4d02-4fc6-b639-34667478827b" />


 
# Verifying that OSPF has been configure properly.

After each router is configured, you can use the following command to verify OSPF has been configured.

<img width="368" height="101" alt="image" src="https://github.com/user-attachments/assets/03bc9d3a-a7f8-4ea1-bdb0-6ba95c125510" />

Show running configuration in the router CLI and find section that start with the text "router ospf (your ospf id)".


# Configure networks for OSPF routing using interface IP addresses and quad-zero masks.

I did everything in advance so I deleted ospf configurations from R2 and R3. I had to use different methods in the excersices.

Configuring router using quad zero wildcard mask specifies the router to use exact interface IPv4 address. The advantage is that no wildcard calculation is required. In all cases area argument will be 0. 

<img width="639" height="155" alt="image" src="https://github.com/user-attachments/assets/7ae81af8-8821-4485-8c1a-5706eef54c15" />

After configuration I verifiend R2 has the correct configuration for OSPF

<img width="660" height="115" alt="image" src="https://github.com/user-attachments/assets/a1e9a7c0-af29-438e-9a7c-878b34e96ca7" />



# Configure OSPF routing on router interfaces 

For router 3 I configured OSPF directly on the interface. 

Router 3 has the following interaces: 
<img width="621" height="79" alt="image" src="https://github.com/user-attachments/assets/9d4d3c2f-a5db-4ecd-8291-a27a7b2c7269" />

To configure OSPF directly to the interfaces I use command 

ip ospf process-id area area-id

<img width="656" height="93" alt="image" src="https://github.com/user-attachments/assets/c4296d3d-f8da-4006-940a-721815f1eb63" />

After configuring each interface I verified that the interfaces were configure correctly from the running configuration. 

<img width="656" height="410" alt="image" src="https://github.com/user-attachments/assets/411fbe85-e30c-457b-9821-6103b570881d" />


## Configure Passive Interfaces

By default all OSPF messages are forwarded out all OSPF-enabled interfaces. These messages should be only sent to interfaces that are connecting other OSPF-enabled routers. Why?`

Unneedeed messages affect LAN networks performance:
Inefficent Use of Bandwidth
Inefficent Use of Resources
Increased Security Risk 

Passive interfaces can be configured on Cisco defices using the following command passive-interface in the routers configuration mode. 

After configuration you can use "show ip protocols" -command to verify interface is listed as passive. 

In this example I need to configure each routers Gigabit -interface with the passive-interface command. This will disable OSPF messages in oter interfaces which do not need to receive OSPF messages. 


<img width="669" height="58" alt="image" src="https://github.com/user-attachments/assets/1355999f-dc7e-43a6-9212-ac144a0f4347" />

As here is shown the GigabitEthernet -interface is listed as a passive interface. 

<img width="661" height="293" alt="image" src="https://github.com/user-attachments/assets/c47c0571-37fe-4915-ac67-a5594bf6bd11" />


And there you go, I have now configured Point-to-Point Single-Area OSPFv2 on a network consisting of Cisco devices.




