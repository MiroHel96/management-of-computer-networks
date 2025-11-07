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

Next I issued following commands to ignore the startupconfiguration and to access the initial configuration. 
- `confreg 0x2142` , modiefies the configuration register to "safemode".
- `reset` - resets the router and allows me on enter to initial configuration mode

<img width="634" height="59" alt="image" src="https://github.com/user-attachments/assets/4660eb06-50dc-4ccf-800d-f10e1a133da4" />


