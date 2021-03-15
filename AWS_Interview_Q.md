Interview Questions
DNS query and recursion
VDI slow login performance
PDC Role
Slow system performance: reasons and troubleshooting tools/steps
Routing and switching concepts
Network and system security
1. What happens when you are accessing the internet
2. Where is DNS configured on Linux
3. if DNS does not work, what happens.
4. if there are several DNS servers but one IP, how can you access a specific DNS server
5. What is different with TCP and UDP
6. How does TCP establish a session
7. How does TCP terminate a session
8. if TCP is terminated abnormally, What happens.
9. How does TCP guarantee the reliability?
10. How can TCP receive lost packet again?

============================================================================

1. What is a service? How can I check the logs of a service? where are they located? How can I check the status of a service? How can I start a service? 
Answer:
Service is an application or set of applications that are running in the background. Services are also known as daemons ending in d.
Logs can be found in /lib/systemd/system
sudo systemctl list-unit-files --type service –all
sudo systemctl | grep running
sudo systemctl status
sudo systemctl start

2. Describe what happens when I boot up my computer
Ans: 
Describe what happens when I boot up my computer Linux
1. BIOS POST
2. Boot loader (GRUB2)
3. Kernel initialization
4. Start systemd, the parent of all processes.

3. How can we check if there is an open connection to a remote host? 
4. Ans : netstat, telnet

4. If you don't remember which arguments you can use with a command, what do you do? 
5. man

Q :Suppose that i'm a client and i cannot connect to a remote server using ssh. How do you troubleshoot this problem ? 
A : Check logs
Do a traceroute
Look at the firewall rules and see if any connections are blocked
Do a DNS troubleshooting - dig, ping

Q: Do you know any tools to configure a firewall?
A : We can use two layers.
1) create Network ACL rules on subnet level.
2) configure Security groups at instance level.
Flag as InappropriateFlag as Inappropriate
If the question relates to Linux I'd answer this way:
1. IPTables
2. firewalld
3. nftables
and many more.

Q: Describe me the 3-way handshake in a simple way 
A :Three way handshake is a way to ensure that a packet was delivered successfully to the destination.
At first the client sends a SYN signal to let the server know that client is about to start communication. Then the server sends a SYN + ACK signal letting the client know that it received the signal from client and sending a signal of its own. Then the client responds with an ACK signal to acknowledge the response from the server. Now a reliable connection is established and the data transfer can be started

Flag as InappropriateFlag as Inappropriate
Client sends SYN signal to server, server acknowledges by sending SYN+ACK signal, client receives the signal and sends and ACK signal back to server and the communication is established for data transfer.

Q: Differences between TCP and UDP 
A : TCP uses 3 way handshake, which ensure delivery of a network packet. UDP cannot guarantee delivery of a packet. TCP can resend lost packages, while UDP cannot. UDP cannot be used for mission-critical packet transfer
TCP: Connection oriented, Maintains sequencing of packets, reliable, protocols: HTTP,FTP,SMTP,etc
UDP: Not connection oriented, no sequencing of packets, unreliable, protocols: DNS,NTP,etc

Q : Why a client should use a cloud infrastructure? 
A : 1. Resilience : how fast it recovers from a damage
2. Elasticity : high level of performace due to more storage and server resources
3. Scalability: Based on traffic you can scale up and down
4. Flexibility: on demand resources
5. Automation: cloud providers take care of all the hardware and security issues

Q : What is a container? 
A : A container is a standard unit of software that packages up code and all its dependencies so the application runs quickly and reliably 
from one computing environment to another. A Docker container image is a lightweight, standalone, executable package of software that includes 
everything needed to run an application: code, runtime, system tools, system libraries and settings.
Set of processes running in a section of resources allocated to it
