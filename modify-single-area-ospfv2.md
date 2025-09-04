# Cisco Packet Tracer - Modify Single-Area OSPFv2

In this excersise my task is to modify already configured single area OSPFv2. 

Topology of the network. 
<img width="730" height="289" alt="image" src="https://github.com/user-attachments/assets/3c77d853-e909-4bfb-b4b3-2aed669d7708" />

Addressing table of the network. 

<img width="798" height="428" alt="image" src="https://github.com/user-attachments/assets/6a598d57-cf28-4bbe-9525-ff54adfd5a30" />


# Modify OSPF Default Settings

I started my modification process by pinging each host from PC1. Everyone responded so connectivity was successfull.

<img width="627" height="487" alt="image" src="https://github.com/user-attachments/assets/ea1d1ad1-3b9b-43b2-b64c-75936222498e" />

I opened R1 CLI to modify my OSPF settings. My task was to modify routers hello and dead timers. 

I used the following commands for R1:
 - interface s0/0/0
 - ip ospf hello-interval 15
 - ip ospf dead-interval 60

<img width="635" height="246" alt="image" src="https://github.com/user-attachments/assets/2589f623-9a26-4439-8518-574f4049d408" />

After issuing command above the OSPF connection with R2 will fail, which is indicated by message in the CLI.

<img width="620" height="86" alt="image" src="https://github.com/user-attachments/assets/15827972-5f18-4b6c-ab72-23f424e8ba55" />

Both sides must have identical settings, so I configured same settings for R2. 


<img width="678" height="584" alt="image" src="https://github.com/user-attachments/assets/19dac401-b839-418e-9b56-a28112199c3d" />

After configuration I waited for a while to get the acknowledgement that R1 and R2 have reestablished OSPF adjacency.

<img width="635" height="48" alt="image" src="https://github.com/user-attachments/assets/97da0a2b-adf3-4c00-9939-953d77c74b59" />

# Adjusting the bandwidth settings on R1 

I traced path from PC1 to Web Server located in network 64.100.1.2.
- tracert 64.100.1.2

  <img width="630" height="176" alt="image" src="https://github.com/user-attachments/assets/d01e60b9-98ec-4ae4-ae1b-9d8a3bd88ebc" />

I configured R1 interface with speed of 64 KB/s. 

<img width="638" height="98" alt="image" src="https://github.com/user-attachments/assets/7d0f040d-ec02-4418-a325-ef5e4be437c3" />

After that I did traceroute again with PC1. As we can see the route changed from R1 to R2 to R1 to R3 and why? OSPF calculates the cost of each route and chooses the one which has least cost to deliver packet. 

<img width="701" height="709" alt="image" src="https://github.com/user-attachments/assets/8e14d4f3-190e-4054-9f2d-a1565d0d9027" />



# Verify connectivity

Finally I pinged each host from PC1 to verify connectivity, which was ok. Now I have modified OSPF hello and dead intervals and modified bandwidth to change router for packets in OSPF setup. 


