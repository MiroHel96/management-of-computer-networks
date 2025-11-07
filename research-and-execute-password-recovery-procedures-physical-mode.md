# Cisco Packet Tracer - Research and Execute Password Recovery Procedures - Physical Mode

In this excercise my objectices are to research and reset the enable password on cisco router. The enable password is protecting privileged EXEC and configuration mode, enable secret password is encrypted and would need to be replaced with a new password. 
Password is reseted by using ROM monitor (ROMMON) mode, it is basic CLI software stored in ROM that can be used in troubleshooting boot error and recover router when IOS is not found. 

Router model in this activity:
- Cisco 2911


Some questions and answers: (Source Microsoft Copilot)

- What is the purpose of the configuration register?
    - Is a 16-bit value determining how the router boots, it controls if startup configuration is loaded from NVRAM, boot source (e.g, flash, TFTP, ROMMON) and console speed and other boot time related behaviors
      
- What command changes the configuration register in global configuration mode?
    - With command `config-register 0xXXXX` you can change the configuration register in global configuration mode.
      
- What command changes the configuration register in ROMMON mode?
    - Using command `confreg 0xXXXX` you can change the configuration register in ROMMON mode. 


Configuration register values and their meanings: 

- 0x2102 - is the default value of most Cisco router and it boots from the IOS image in flash, loads startup configuration from NVRAM and is used for normal operation.

- 0x2142 - is a value that ignores the startup configuration, bootsd from the IOS image in flash, ingnores or skips saved configurations and is used for troubleshooting and password recovery. 


## Password recovery documented in Cisco Packet Tracer

1. I connect to the router using terminal from the laptop.
2. Turn off the router from the powerswitch.
3. Open the terminal connection and quickl press `CTRL-c` or type `ALT-b`, before the router finishes loading to access ROMMON mode.

As we can see from the picture I have now enabled ROMMON mode in the router. 

<img width="697" height="710" alt="image" src="https://github.com/user-attachments/assets/664d270d-539b-4493-8097-a6d9cc7b7783" />

Next I issued following commands to ignore the startupconfiguration and to access the initial configuration prompt.
- `confreg 0x2142` , modiefies the configuration register to "safemode".
- `reset` - resets the router and allows me on enter to initial configuration mode if needed.

I entered `N` to not enter the initial configuration mode. 

<img width="634" height="59" alt="image" src="https://github.com/user-attachments/assets/4660eb06-50dc-4ccf-800d-f10e1a133da4" />

<img width="699" height="714" alt="image" src="https://github.com/user-attachments/assets/f6697ce7-fce6-409b-afd0-737788244630" />


Next I copied the running configuration to startup configuration. After that I continued to change the routers passwords.

<img width="638" height="283" alt="image" src="https://github.com/user-attachments/assets/8dfaa8af-9e17-405f-b77b-8ab8bd44789c" />

Next I configured the following settings for the router. 
- hostname `Branch`
- password `branch1`
- console vty line passsword `brach2`
- banner `Password Recovered`

<img width="631" height="102" alt="image" src="https://github.com/user-attachments/assets/5d5067a7-ffad-4de7-a7b1-625b4f8c7c63" />

<img width="601" height="103" alt="image" src="https://github.com/user-attachments/assets/db3842cd-552b-4529-8815-06b21f5c674f" />

<img width="628" height="187" alt="image" src="https://github.com/user-attachments/assets/29dbf4fe-e7e5-468d-a98c-ad24842d0620" />

We can verify that the confreg version is `0x2142` with the command `show version`.

<img width="634" height="215" alt="image" src="https://github.com/user-attachments/assets/b2b6f649-7319-44c2-b9eb-4cbec1a1ae47" />

Next I changed the configruration register version to `0x2102` with the command `config-register 0x2102`. Finally I verified its configuration with `show version` command. 

<img width="634" height="354" alt="image" src="https://github.com/user-attachments/assets/87ad12fe-fedd-49a6-82e6-fd1d82690d61" />

I had to enable interfaces `G0/0` and `G0/2` and after that I reloaded the router. It now asks a password while connecting with console cable. After testing the passwords everyting works as expected. I have now reseted unknown passwords for Cisco Router.

<img width="633" height="547" alt="image" src="https://github.com/user-attachments/assets/9014cf80-e6af-4680-854a-94ff94d050dd" />

<img width="636" height="190" alt="image" src="https://github.com/user-attachments/assets/fb09a9ed-08a8-42e5-bfa3-29aac1cc6b6e" />


  

