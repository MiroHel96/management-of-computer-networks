##Router Configuration with Cisco Packet Tracer

In this document I configure router routing table in a LAN. Router is connected to two host machines with straight throug cable.

##Starting situation
<img width="724" height="530" alt="image" src="https://github.com/user-attachments/assets/ec6da85c-0151-4acd-8c9e-25155826533a" />

After I opened Cisco Packet Tracer, I created general router and two host computers. I connected them to eachother with straight throughcable and opened my router to configure it's initial settings. 

Configurations for the router were: 

Interface GigabitEthernet 0/0 - 192.168.10.1 255.255.255.0

Interface GigabitEthernet 0/2 - 192.168.20.2 255.255.255.0

###Interface IP address configuration
<img width="701" height="717" alt="image" src="https://github.com/user-attachments/assets/a8be8e3d-5e4e-47d1-b1f9-55e4d9b98160" />

###Interfaces status after configuration
<img width="706" height="710" alt="image" src="https://github.com/user-attachments/assets/8121fd77-b80d-4f26-9a19-0705ab5f28a6" />

After Configuring setting for the router I configured both host devices with the following settings:

PC1:
- IPv4 192.168.20.2
- Subnet Mask 255.255.255.0
- DW 192.168.20.1

PC2:
- IPv4 192.168.10.2
- Subnet Mask 255.255.255.0
- DW 192.168.10.1

After setting host setting I conducted ping test from the router and from the hosts to check networks operability. Everything worked fine as expected in straigh connection.

Finaly I opened the router and checked its Route table. 

##Routers routing table
<img width="688" height="185" alt="image" src="https://github.com/user-attachments/assets/62639dd3-8883-4112-88a9-6aea65f38e09" />

  
