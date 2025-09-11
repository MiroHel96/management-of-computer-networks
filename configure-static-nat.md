# Cisco Packet Tracer - Configure Static NAT

## Network topology

<img width="796" height="382" alt="image" src="https://github.com/user-attachments/assets/a041827c-dabd-4d5c-9c0d-e013472f0c6b" />


# Test Access without NAT

First I tested could I connect to the Web Server from PC1 Web Browser. 

<img width="699" height="711" alt="image" src="https://github.com/user-attachments/assets/46027efc-0740-4d6e-8002-0b0371aeb91d" />

The website did not open.


Next I pinged R1 from PC1 and the test was successful.

<img width="704" height="712" alt="image" src="https://github.com/user-attachments/assets/97051925-3e5e-43e6-b084-a5439ac813be" />

After pinging R1 I opened it's CLI and issued the following commands: 
 - show run | include nat , searches words including "nat" from the configuration
 - show ip nat translations, shows the routing table.

<img width="699" height="714" alt="image" src="https://github.com/user-attachments/assets/30c78e3b-c102-44ff-86c8-4bdff1e9c3c5" />

show run | include nat explained more in detail from Microsoft Copilot

<img width="908" height="933" alt="image" src="https://github.com/user-attachments/assets/6683de26-17c4-4817-a001-ac8e1c190897" />

There were no configurationms for nat and therefore devices could not reach network 172.16.16.0/28.


# Configure Static NAT 


# Test Access with NAT 

 

 
