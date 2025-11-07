# Cisco Packet Tracer - Research and Execute Password Recovery Procedures - Physical Mode

In this excercise my objectices are to research and reset the enable password on cisco router. The enable password is protecting privileged EXEC and configuration mode, enable secret password is encrypted and would need to be replaced with a new password. 
Password is reseted by using ROM monitor (ROMMON) mode, it is basic CLI software stored in ROM that can be used in troubleshooting boot error and recover router when IOS is not found. 

Router model in this activity:
- Cisco 2911


Some questions and answers: 

- What is the purpose of the configuration register?
- What command changes the configuration register in global configuration mode?
- What command changes the configuration register in ROMMON mode?


Configuration register values and their meanings: 

- 0x2102
- 0x2142


