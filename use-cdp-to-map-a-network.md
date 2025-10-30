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
  



