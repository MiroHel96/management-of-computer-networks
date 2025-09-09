# Cisco Packet Tracer - Configure Named Standard IPv4 ACLs

Topology of the network 
<img width="1178" height="666" alt="image" src="https://github.com/user-attachments/assets/78933216-75f9-434a-8d3e-f374d8cda6c8" />

Addressing table 
<img width="1110" height="488" alt="image" src="https://github.com/user-attachments/assets/8f3f4399-a64c-4dbd-9e2a-802951bc8a86" />

# Configure and apply a named standard ACL

First is tested my networks connectivity by pinging Webserver and File Server from each workstations. 

PC1 
<img width="1396" height="1422" alt="image" src="https://github.com/user-attachments/assets/57f91907-809a-46f4-a1dc-911809992d2f" />

PC0
<img width="1392" height="1410" alt="image" src="https://github.com/user-attachments/assets/db09390d-3085-46c3-8ddf-fbefb48b0a86" />

PC2
<img width="1396" height="1414" alt="image" src="https://github.com/user-attachments/assets/344e88aa-5387-4f0a-98c7-43b6ee44f42b" />

Ping -test was succesfull, now I have to configure named standard access lists for the router. I used the following commands for them: R1(config)# ip access-list standard File_Server_Restrictions
R1(config-std-nacl)# permit host 192.168.20.4
R1(config-std-nacl)# permit host 192.168.100.100
R1(config-std-nacl)# deny any

## Configuring R1 for the File Server


<img width="1272" height="700" alt="image" src="https://github.com/user-attachments/assets/2e49a3cb-36d2-4745-84eb-1422f086daf6" />

<img width="1266" height="374" alt="image" src="https://github.com/user-attachments/assets/d09c50f9-21fd-4522-8dc7-516d7a343dad" />


# Apply the named ACL.

After creating the ACL I must now apply it to the corrext interface which is Fast Ethernet 0/1.

<img width="1250" height="638" alt="image" src="https://github.com/user-attachments/assets/8a6a348b-3003-4c57-8dd1-a72768022be8" />



# Verify the ACL Implementation

<img width="922" height="184" alt="image" src="https://github.com/user-attachments/assets/953dbc76-9363-43bf-ab55-d2e25b31668e" />

