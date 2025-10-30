## Cisco Packet Tracer - Use CDP to Map a Network

### Network topology and addressing table 

<img width="627" height="246" alt="image" src="https://github.com/user-attachments/assets/30241d29-8e16-45e7-b46e-01eb989ed302" />


<img width="775" height="486" alt="image" src="https://github.com/user-attachments/assets/b5937270-b17e-417f-893c-07b69e2f2411" />

In this Packet Tracer activity I must map Remote Branch Office network and discover recently intalled switch.

## Use SSH to Remotely Access Network Devices 

My first step was to remotely connect to Edge1 router with SSH from Admin-pc. 

I opened the PC and inputed edger routers ip address `192.168.1.1` and username `admin01`.

<img width="699" height="706" alt="image" src="https://github.com/user-attachments/assets/2462d967-f569-4bcd-a234-9c86ed28a8d3" />

After loggin in to the router I inspected its interfaces using command `show ip interfaces brie` and `show interfaces`.

<img width="701" height="701" alt="image" src="https://github.com/user-attachments/assets/8208902d-2a2d-4144-8ea4-2671715fa3e0" />

From the addressing table the following information is missing: 

- Serial 0/0/0, IP Address `209.165.200.5` and CIDR (Classless Inter-Domain Routing) `/30`.
- Serial 0/0/0,  CIDR (Classless Inter-Domain Routing) `/30` also.

  Next I remotely connected to Remote Branch Office with the following command `ssh -l remote branchadmin 209.165.200.10`. I logged in with the activitys password.

  <img width="701" height="701" alt="image" src="https://github.com/user-attachments/assets/43e943e8-da6e-4203-ba89-e65f0f2722f9" />
  
## Use CDP to Discover Neighboring Devices 

After logging in to the Remote Branch Office, I issued the following command `show cdp` to see if CDP is enabled. It was not according to the output.

<img width="640" height="78" alt="image" src="https://github.com/user-attachments/assets/58ad2c6e-d1c9-4298-895d-19d90e85bd11" />

Next I had to turn on CPD. I opened routers configuration mode with the command `configure terminal`. I needed issued command `cdp run` to enable cpd to run it globally on all supported interfaces. 

<img width="640" height="73" alt="image" src="https://github.com/user-attachments/assets/8e31aece-4c82-40af-bf8a-467c5fa73f9d" />

I only wanted to broadcast CDP information to the Remote Branch Office network so I disabled CDP messages from interface `serial 0/0/1`. 

<img width="629" height="145" alt="image" src="https://github.com/user-attachments/assets/dba653db-a71f-4a01-a9ac-b06781d0f38e" />


## Verifying CDP

As we can see CDP is no active and sending packets. 

Command `show cdp`

<img width="629" height="84" alt="image" src="https://github.com/user-attachments/assets/0c0497e0-b18a-4e11-a490-cbddb53249b5" />

Command `show cdp neighbors`

<img width="634" height="100" alt="image" src="https://github.com/user-attachments/assets/a861d936-622a-457a-89fc-58257d7e1a38" />

Command `show cdp neighbors detail`

<img width="628" height="287" alt="image" src="https://github.com/user-attachments/assets/9e04be5c-feb9-4c67-b1ea-8307d521c1c9" />


As we can see neigboring device is Branch Networks Firewall. 




