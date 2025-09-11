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

No that I know PC1 or L1 cannot connect to the Server1 I must configure R1 with static NAT. 
We need to map Server1 addresses to NAT translation which are:
- 172.16.16.1, inside
- 64.100.50.1, outside

I issued the following commands to configure R1 with static NAT:
- ip nat inside source static 172.16.16.1 64.100.50.1

After NAT configuration I applied it to Interface G0/0, with command "ip nat inside". Finally I configured s0/0/0 interface as an outside interface. 


<img width="702" height="711" alt="image" src="https://github.com/user-attachments/assets/c1f1ef89-eb55-44f1-a578-27a161dc6917" />

<img width="632" height="412" alt="image" src="https://github.com/user-attachments/assets/6ac988f5-c8e9-4b85-9bd3-ade616279f64" />

<img width="631" height="88" alt="image" src="https://github.com/user-attachments/assets/a5c2ff56-ef7b-4ee6-bb9d-45b164b25344" />


# Test Access with NAT 

Finally I tested that the NAT is configured correctly by pinging Server 1 from PC1. 

<img width="703" height="711" alt="image" src="https://github.com/user-attachments/assets/dac1bc46-ff74-4c55-81f0-b4a38d84c3cf" />
 
 <img width="637" height="116" alt="image" src="https://github.com/user-attachments/assets/8074a542-d5e2-4e7a-af57-064b2ad66152" />

Now I have configured simple static NAT and that's the end of this excersise. 
 
