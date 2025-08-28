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


