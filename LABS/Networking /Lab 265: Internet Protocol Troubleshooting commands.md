                      LAB 265 - Internet Protocol Troubleshooting commands
**Overview**

In this lab, I explored how to practice troubleshooting commands and to test connectivity to and from a launched EC2 instance through running the ping command. I learnt that the ping command is used this to test connectivity and ensure that it allows Internet Control Message Protocol (ICMP) requests on the security level, such as security groups and network ACLs. This was done through a simulated practice similar to a real life scenario where one would have to assist a customer in helping the customer address their issues which gave it a different element and offered a great and practical learning moment.
                      
                      Key Objectives
1. Practice troubleshooting commands
2. Get an understanding of the layers and how troubleshooting commands flow with the Open Systems Interconnection (OSI) model
3. In depth understanding of the Ping, Traceroute, Netstat, Telnet and Curl command
4. Identify how these commands can be used in customer scenarios

                   Process followed- Tasks breakdown

**Task 1: Use SSH to connect to an Amazon Linux EC2 instance**
This lab was also centered around a scenario provided by a customer and I had the network administrator role who was responsible for troubleshooting customer issues which will be mentioned in greater detail in the next task. The first task involved connecting to an Amazon Linux EC2 instance using an SSH utility to perform the required operations.

**Task2: Practice troubleshooting commands**

I got an understanding of the Application, Transport and Network layers where the I applied the ping, traceroute, netstat, telnet and curl commands to address customer quiries. There are layers that have commands related to them to help with troubleshooting, and the diagram below will illustrate an example of how the troubleshooting commands flow with the Open Systems Interconnection (OSI) model:
<img width="2270" height="1384" alt="image" src="https://github.com/user-attachments/assets/265b0967-b70f-435c-b86b-5875664f2e7e" />

**Network layer: Ping and Traceroute commands**
For the ping command, you can input an IP or URL followed by options such as: ping 8.8.8.8 -c 5 where the -c stands for count, and 5 stands for how many requests you are requesting. The ping command is used to test connectivity to something such as a server through sending ICMP echo requests from your machine to the server that you are trying to reach (for example, amazon.com). The server sends an echo reply with a round-trip time. The ping can also be used to troubleshoot connectivity issues and reachability to a specific target and to bring a specific network up if traffic needs to continuously flow through a network which can be done through sending a continuous ping.
The traceroute command can be used to investigate the path and latency that the packet takes to get from your machine to the destination (8.8.8.8), where each server is called a hop. There can be some packet loss, seen as percentages, at each loss, which is usually due to the user's local area network (LAN) or ISP. The possible outcomes are that if the packet loss occurs toward the end of the route, then the issue is more than likely the server connection, but If the loss is toward AWS, you might need to investigate other factors that might limiting networking connectivity.
<img width="2880" height="1800" alt="image" src="https://github.com/user-attachments/assets/b7667fa8-0277-402d-a41d-e3a3b110e7ed" />

**Transport layer: Netstat and Telnet commands**
The netstat command can be run in the following scenario: A company is running a routine security scan and found that one of the ports on a certain subnet is compromised. 
Netstat will be used to confirm the local host on that subnet to confirm if the port is listening when it shouldn't be. The netstat command does this through showing the current established TCP connections from which the host is listening. When you have to troubleshoot networking issues starting with the host machine and working outward, netstat can be run to understand which ports are listening and which are not which will provide you with a snapshot of your layer 4 connectivity and help you save time when trying to narrow down a large networking issue.
The Telnet command can be used for the following scenario: A customer has a secure web server and has custom security group rules and network ACL rules configured, and they are concerned that port 80 is open even though it shows their security settings indicate that their security group is blocking this port. 
Part of the resolution is that you can run telnet 192.168.10.5 80 to ensure that the connection is refused which is done through the command confirming the TCP connection to a web server making an HTTP request if using port 80 to telnet. The possible outcomes are that If you can successfully connect to the web server, then there is nothing blocking you or the server from connecting, and if the connection fails with a message like "connection refused," then something is likely blocking the connection, such as a firewall or security group. If the connection fails with a message like "connection timed out," then then issue may be no network route or connectivity. It was interesting to note that the telnet command can be used at layer 7 as well.


