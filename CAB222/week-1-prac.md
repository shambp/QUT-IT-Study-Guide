# Practical
Week 1's practical revolves around using the wireshark tool to monitor traffic within a peer to peer connection.

## Task 1
### Configuring the connections
Edit the ethernet settings through ```network settings -> ethernet -> change adapter options -> properties -> and configuring the IPV4 internet protocol setting``` on two computers (or in the case of the prac 2 virtual machines). give them both a simple yet UNIQUE IP address, e.gg 192.169.1.2 and 192.168.1.3

### Testing the connection
first disable the firewall on both ends, then open cmd and pinging the other VM (eg ping 192.168.1.3 if i am using the vm with .1.2).

### Wireshark
open wireshark, run the ping again and observe the test packets being transferred between the two systems.

you can also click on the little dropdown boxes (bottom left by default) you can view more information like the destination mac adress and destination ip address etc.

## Task 2
### move from peer to peer into a "home network"

### reconfig VM's
within the vm menu create a new network (specificaly NAT) and change each vms settings to a nat connection (by going through the settings menu and changing there).

### change ethernet settings
go back into each of the vms and revert the change to the ipv4 settings done earlier (changing them to automatically connecting),

### get ips
in cmd type ipconfig to grab each of the vms ip address, and then ping eachother again. observing everything through wireshark.
# Week 1 prac is done