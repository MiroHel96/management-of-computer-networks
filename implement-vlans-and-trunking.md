# Cisco Packet Tracer - Implement VLANs and Trunking

In this excersise I configure VLANs, ports for VLANs, configure Static Trunking and Dynamic Trunking. 

Network topology 
<img width="865" height="347" alt="image" src="https://github.com/user-attachments/assets/3722e198-5c2e-4076-a3cc-4aca98886305" />

Network Addressing Table 
<img width="1032" height="365" alt="image" src="https://github.com/user-attachments/assets/266f2774-0f6e-4baf-8f05-442aa38503bf" />



# Part 1 Configure VLANs

I started to configure each switch in the network accodring the VLAN Table.

VLAN Table for configurations
<img width="712" height="221" alt="image" src="https://github.com/user-attachments/assets/55daa77b-3333-4e7f-931f-4ab1f1357226" />

I started from SWB.

<img width="633" height="413" alt="image" src="https://github.com/user-attachments/assets/72a6ad8b-ff2c-4759-9e76-441e0d837a01" />

<img width="631" height="314" alt="image" src="https://github.com/user-attachments/assets/dad4d6e0-c018-4d85-bbb5-e6600b472f39" />

# Part 2 Assign Ports to VLANs

After configuring VLANs and names for them, I configured correct interfaces and VLAN for themm.

<img width="634" height="397" alt="image" src="https://github.com/user-attachments/assets/aef49390-0d79-4d12-a1bb-04a66bf14387" />

<img width="633" height="316" alt="image" src="https://github.com/user-attachments/assets/b47f6594-d91a-4bdc-a6a2-805f7b684c9c" />

I did same steps for SWC as for SWB. I also configured voice for FastEthernet0/4 for SWC.

<img width="642" height="382" alt="image" src="https://github.com/user-attachments/assets/ee8c6f3c-51cb-4756-b5a1-0518e37bc3a9" />

<img width="638" height="349" alt="image" src="https://github.com/user-attachments/assets/5e1d12ac-17b7-48af-b344-5e4407b98149" />

After configuring voice for SWC I had to configure virtual management interfaces for each switch. 

Configuration for SWA.
<img width="634" height="203" alt="image" src="https://github.com/user-attachments/assets/e7e7842a-c6e4-4152-ad22-677c2b53db00" />

I did the same configurations for SWB and SWC and used correct IP addresses from the Addressing table.

# Part 3 Configure Static Trunking 

Next I configured static Trunking for connection between SWA and SWB. I also disabled dynamic trunking from that port. 

<img width="637" height="285" alt="image" src="https://github.com/user-attachments/assets/9c2425b1-edf6-46d1-9187-4421727f1555" />

Disabling dynamic trunking
<img width="631" height="71" alt="image" src="https://github.com/user-attachments/assets/24077d98-d42e-42af-acf0-6c2831329722" />

After that I did same cofigurations for SWA and finally I configured the trunk to use native VLAN.

<img width="637" height="156" alt="image" src="https://github.com/user-attachments/assets/ce28dfae-375a-4d10-814e-cf5b9b955fb2" />

When both switches have the same settings Native VLAN issues are eliminated. 

<img width="631" height="420" alt="image" src="https://github.com/user-attachments/assets/3db1e71b-11b7-41aa-9fab-043e14c13e86" />


# Part 4 Configuire Dynamic Trunking 

Final part of this excersise was to configure dynamic trunking for SWA and SWC. According to the excersise I can assume that SWC is setr to the default DTP mode for 2960 swtiches. So therefore I only configure SWA with dynamic trunking mode. I was not sure should I use auto or desirable but desirable was the correct for this one. 

<img width="631" height="340" alt="image" src="https://github.com/user-attachments/assets/1547f1c0-38ad-4ff4-afde-222e8a3e79bf" />

After that everyting was configured as expected, but I forgot to configure VLANs for SWA. I did that and finally my score was 100% 

<img width="637" height="355" alt="image" src="https://github.com/user-attachments/assets/21382718-7ab9-46c1-9cd7-66854e1a7258" />


<img width="583" height="268" alt="image" src="https://github.com/user-attachments/assets/232970f7-2940-48ba-9224-9780f9a39b8d" />



