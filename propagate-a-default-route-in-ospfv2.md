# Packet Tracer - Propagate a Default Route in OSPFv2


Network topology. 

<img width="797" height="339" alt="image" src="https://github.com/user-attachments/assets/26eca5e4-d608-46be-83cc-7b38d64807a2" />


Network Addressing table.

<img width="943" height="424" alt="image" src="https://github.com/user-attachments/assets/9e3cb6a0-c1e4-4223-ac82-fe50adcf9bb0" />


# Propagate a Default Route

First I attempted to ping Web Server in 64.100.1.2 network from PC1, PC2 and PC3. The destination host was unreachable from each PC.

PC1 
<img width="698" height="707" alt="image" src="https://github.com/user-attachments/assets/20227c62-1004-4b5c-960d-ba196ced5bde" />

PC2
<img width="704" height="715" alt="image" src="https://github.com/user-attachments/assets/1585032a-0eaa-4d56-b82f-2e65058235de" />

PC3
<img width="701" height="709" alt="image" src="https://github.com/user-attachments/assets/b1765279-5ef3-4af7-8ebb-718f335013f2" />

Because the ping failed I had to check R1, R2 and R3 routing tables for information. 

R1
<img width="631" height="384" alt="image" src="https://github.com/user-attachments/assets/881f0d4a-f704-444f-80a0-ab3c6932e49e" />

R2
<img width="636" height="435" alt="image" src="https://github.com/user-attachments/assets/315461cb-a230-40c6-8866-69e899759e7d" />


R3
<img width="635" height="496" alt="image" src="https://github.com/user-attachments/assets/7b5e4ad2-da25-4332-8b2f-a06dd0984e8b" />


# Configure R2 with directly attached default route to the internet

I Configured R2 with the following command to create a default route:
 - R2(config)# ip route 0.0.0.0 0.0.0.0 Serial0/1/0

   <img width="658" height="104" alt="image" src="https://github.com/user-attachments/assets/ea7de6a2-9c93-4cdf-9b03-eb85c23fac74" />

  After interface configuration for default route, I propagatet the route in OSPF so other routers would learn it.

  <img width="635" height="104" alt="image" src="https://github.com/user-attachments/assets/f16dde61-a837-4068-b806-56a0c20c9713" />

R3
<img width="578" height="46" alt="image" src="https://github.com/user-attachments/assets/9a05f775-de32-4ca1-9b7e-0e60b75687a2" />

R1
<img width="413" height="29" alt="image" src="https://github.com/user-attachments/assets/b90ccaac-3754-45ba-80de-a43838f88835" />

Finally I veriefied connectivity by pinging the server from PC1, PC2 and PC3.

# Verify connectivity 


