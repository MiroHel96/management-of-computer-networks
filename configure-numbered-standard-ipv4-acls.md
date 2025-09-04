# Cisco Packet Tracer Configure Numbered Standard IPv4 ACLs

In this excersise I configure standard ACLs. 

Topology of the network

<img width="673" height="489" alt="image" src="https://github.com/user-attachments/assets/1844b609-6269-486e-ad81-a5de6e3728c6" />

Addressing Table of the network 

<img width="889" height="424" alt="image" src="https://github.com/user-attachments/assets/7cce26ea-ad3b-4845-a3b9-96031a5c83cd" />


# Plan ACL implementation

Firs step was to test networks connectivity. I used ping -command form PC1 to ping PC2, PC3 and PC4.

<img width="705" height="711" alt="image" src="https://github.com/user-attachments/assets/c5608145-70e7-4a2d-95e2-ac607b452ebb" />

After that 

# Configure and apply a numbered standard ACL on R2

## Router 2 numbered standard ACL

First task was to create an ACL rule for R2. Devices from network 192.168.11.0 /24 should not be able to access WebServer in network 192.168.20.0/24. 

I opened R2 and did the following configuration rules for the router:
- R2(config)# access-list 1 deny 192.168.11.0 0.0.0.255
- access-list 1 permit any

and finally I verified my access list contents. 
show access-lists

<img width="631" height="369" alt="image" src="https://github.com/user-attachments/assets/244d075f-921f-4ee1-8362-96e079007993" />


Now I have done ACL rules for my router, I must apply the rules for an interface to make them actually do packet filttering. 

I issued the following command for R2 G0/0 interface: 
R2(config)# interface GigabitEthernet0/0
R2(config-if)# ip access-group 1 out 

Out in the final command means that outbound traffic is effected on the interface. Inbound can get through. 

<img width="632" height="338" alt="image" src="https://github.com/user-attachments/assets/f280b4dd-6f57-42c7-920c-977180fb71b9" />

## Router 3 numbered standard ACL




