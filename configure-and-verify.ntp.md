# Cisco Packet Tracer - Configure and Verif NTP 

In this activity I configure and verify NTP protocol for Cisco Routers. 

Network Topology 

<img width="649" height="295" alt="image" src="https://github.com/user-attachments/assets/e6ecf36d-96cb-46e4-a471-7fd22859cefa" />


Addressing Table 

<img width="749" height="194" alt="image" src="https://github.com/user-attachments/assets/5e3aed8d-9037-4016-8a9f-61c388e82432" />


## Part 1 NTP Server 

In this activiy NTP has already been configured for the server. I only needed to verify its configuration from services. I opened the servers `Services` tab and as we can see from the picture belows the services in turned on. 

<img width="709" height="705" alt="image" src="https://github.com/user-attachments/assets/84d199c0-8185-46ea-a4b4-84736c14623e" />

Next I tested connectivity by pinging the NTP server from `Router1` and `Router2`. Both routers are connected and communicating with the server.

<img width="632" height="122" alt="image" src="https://github.com/user-attachments/assets/963318a5-f0e9-46fa-8cab-fa93658267db" />


## Part 2 configure The NTP Clients

Next I configured NTP for both clients. 

You can check NTP status with the command `show ntp status`, as we can see from the photo, NTP is not enabled on R1. 

<img width="641" height="106" alt="image" src="https://github.com/user-attachments/assets/b49915d2-5c8b-4142-b66f-7ffc447edf1e" />

Using command `show clock detail` we can see the time of the device and source of the time. 

<img width="633" height="73" alt="image" src="https://github.com/user-attachments/assets/b46598b9-293d-4e72-8ae7-87b332c7b811" />

Next I configured NTP for R1 using the command `ntp server 209.165.200.225` in configuration mode. After that I configured same settings for R2.

<img width="639" height="455" alt="image" src="https://github.com/user-attachments/assets/0e3f7d54-83f6-44fd-bfb0-cca54099330c" />

<img width="634" height="522" alt="image" src="https://github.com/user-attachments/assets/6fdc785e-d9ac-4ae2-b306-abb614fb0611" />

R1 and R2 clocks have not been yet synchronized, therefore I fast forwarded time in Packet Tracer. After waiting for a moment, we can see that the NTP time is synchronized with the Routers. Example R1 below. 

<img width="638" height="169" alt="image" src="https://github.com/user-attachments/assets/9951b9df-98b9-4a8f-83b3-8fb5202d1266" />

We can also check NTP associations with command `show ntp associations`

<img width="636" height="119" alt="image" src="https://github.com/user-attachments/assets/c4b74a22-c365-4e8d-b7b6-0587096ae3ef" />


