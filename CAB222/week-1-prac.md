# Practical
Week 1's practical revolves around using the wireshark tool to monitor traffic within a peer to peer connection.

## Configuring the connections
Edit the ethernet settings through ```network settings -> ethernet -> change adapter options -> properties -> and configuring the IPV4 internet protocol setting``` on two computers (or in the case of the prac 2 virtual machines). give them both a simple yet UNIQUE IP address, e.gg 192.169.1.2 and 192.168.1.3

## Testing the connection
first disable the firewall on both ends, then open cmd and pinging the other VM (eg ping 192.168.1.3 if i am using the vm with .1.2).

## Wireshark
open wireshark, run the ping again and observe the test packets being transferred between the two systems.

# Week 1 prac is done