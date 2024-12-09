There are in total 12 devices.

Initial commit:
1 Router (1941)
2 Switches (2960-24TT)
2 PC's connected to the 1st switch (PC-PT) (IP addresses: 168.90.0.5 and 168.90.0.3)
1 Laptop connected to the 1st switch (Laptop-PT) (IP address: 168.90.0.2)
1 Server connected to the 1st switch (Server-PT) (IP address: 168.90.0.4)
1 PC connected to the 2nd switch (PC-PT) (IP address: 210.3.14.2)
2 Server's connected to the 2nd switch (SERVER_PT) (IP addresses: 210.3.14.3 and 210.3.14.4)

Update:
Added 2 new devices
1 PC to the 1st switch (PC-PT) (IP address: 168.90.0.6)
1 PC to the 2nd switch (PC-PT) (IP address: 210.3.14.5)

Commands used:
-CONFIGURING the router interfaces:
enable
configure terminal
interface GigabitEthernet0/0
ip address 168.90.0.1 255.255.0.0
no shutdown
exit
interface GigabitEthernet0/1
ip address 210.3.14.1 255.255.255.0
no shutdown
exit

ENABLING DHCP FOR EACH NETWORK:
1st:
ip dhcp pool NET1
network 168.90.0.0 255.255.0.0
default-router 168.90.0.1
2nd:
ip dhcp pool NET2
network 210.3.14.0 255.255.255.0
default-router 210.3.14.1

After this i manually clicked on each PC, Server etc to set the IP configuration to DHCP
I verified the configuration using the "ipconfig" command on each node
And then i pinged other devices from each device
