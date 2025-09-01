# Cisco Packet Tracer Determine the DR and BRD 

In this excersise I examine DR and BDR Changing roles and modify OSPF Priority and Force Elections 

Topology of the excersise

<img width="671" height="387" alt="image" src="https://github.com/user-attachments/assets/242026c6-75be-4a80-bb02-2639a9e85652" />

Adressing Table 

<img width="878" height="237" alt="image" src="https://github.com/user-attachments/assets/dcf5b2a8-9235-44e5-a20f-224de8114bb5" />



# Part 1 Examine DR and BRD Changing roles

I first examined each router for its current DR (Designated Router) and DBR (Backup Designated Router) with command "show ip ospf neighbor".

Example from RA
<img width="703" height="717" alt="image" src="https://github.com/user-attachments/assets/184b7cd0-6257-46f0-8e93-0b2b3f863a42" />

Example from RB

<img width="705" height="712" alt="image" src="https://github.com/user-attachments/assets/f5e22aaa-ec49-4496-b04c-411baf838526" />

Example from RC

<img width="702" height="708" alt="image" src="https://github.com/user-attachments/assets/04ab69b4-1eca-470a-a1ad-b04c9c47e201" />

Roles for the routers according topology and addressing table.

Full/Drother - the router is not DR OR BRD.
Full/DR - routher is the Designated Router
Full/BDR - router is the Backup Designated Router

RA 192.168.31.11 1 is FUll/Drother, so it means RA is not either DR or BR. 

RB 192.168.31.22 is FULL/BDR, so it is the Backup Designated Router.

Finally RC 192.168.31.33 is FULL/DR, which indicates that it is the Designated Router. 

# Turn on IP OSPF adjacency debugging.

Before testing DB and DBR role changes, I have to turn on IP OSPPF adjacency debugging.

I entered the following command to RA and RB "debug ip ospf adj".

<img width="635" height="42" alt="image" src="https://github.com/user-attachments/assets/6e64b650-406b-4f21-9877-9bcd44f52815" />


# Disable the GigabitEthernet0/0 interface on RB

Next I disabled G0/0 interface on the RC by using the command "shutdown" in the interface configuration.

<img width="699" height="652" alt="image" src="https://github.com/user-attachments/assets/48f7db51-ba77-48d4-b9a8-8c07b9da8038" />

According to the debugging output, DR is not 192.168.31.22 which is RB nad BDR is now 192.168.31.11 and that is RA.

<img width="812" height="531" alt="image" src="https://github.com/user-attachments/assets/7120ff66-87ce-4ace-a0fd-eb62f7d6154f" />

# Restore G0/0 interface on RC

After testing successfully role changes in DR and BDR I turned on the interface to revert the roles back to original routers. This simulation was a test if the router would lose its connection.

<img width="631" height="132" alt="image" src="https://github.com/user-attachments/assets/daf54b9e-d426-4b60-97c4-a916ced03003" />

Routers state returned back to normal. RB is now DR abd RA is the BDR.
<img width="635" height="131" alt="image" src="https://github.com/user-attachments/assets/f7679d2f-01c8-4b83-9229-72a18c54698b" />




# Part 2 Modify OSPF Priority and Force Elections 

 
