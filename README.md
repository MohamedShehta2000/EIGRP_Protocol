# Title :
#### Understanding EIGRP: The Enhanced Interior Gateway Routing Protocol

# Introduction
#### EIGRP is a dynamic routing protocol used on a computer network for automating routing decisions and configuration. Originally developed by Cisco, EIGRP is an advanced version of IGRP (Interior Gateway Routing Protocol) and provides improvements in speed, scalability, and efficiency.

# Table of Contents
#### 1.What is EIGRP?
#### 2.EIGRP vs. Other Routing Protocols (OSPF, RIP)
#### 3.Key Features of EIGRP
#### 4.EIGRP Metrics and Calculation
#### 5.EIGRP Packet Types
#### 6.Configuration of EIGRP on Cisco Routers
#### 7.Advanced EIGRP Concepts (Feasible Successor, DUAL Algorithm)
#### 8.Troubleshooting EIGRP
#### 9.Conclusion

# 1. What is EIGRP?
#### EIGRP is a hybrid routing protocol that combines the features of both distance vector and link-state protocols. It allows routers to share information within a network quickly and efficiently.

#### ![Design 1](https://github.com/user-attachments/assets/79c085ec-f13f-41ea-8ba7-0d98c4101f8b)

####Type: Distance-vector (with some link-state features)
#### Metric: Bandwidth, delay, load, reliability
#### Administrative Distance (AD): 90 for internal routes, 170 for external routes

# 2. EIGRP vs. Other Routing Protocols (OSPF, RIP)
### Protocol	               Type	                       Metric    	                                Convergence Time	                  Scalability
### RIP	                     Distance-vector	          Hop count                                         Slow                             	Low
### OSPF	                   Link-state               	Cost (based on bandwidth)	                        Fast                              High
### EIGRP                    Hybrid	                    Bandwidth, delay, load, reliability	              Fast	                            High


# 3. Key Features of EIGRP
#### Fast Convergence: Uses DUAL (Diffusing Update Algorithm) to achieve rapid convergence.
#### Efficient Bandwidth Usage: EIGRP sends partial updates rather than full updates.
#### Classless: Supports VLSM (Variable Length Subnet Mask) and CIDR (Classless Inter-Domain Routing).
#### Load Balancing: Supports equal and unequal cost load balancing.

# 4. EIGRP Metrics and Calculation
## EIGRP uses a composite metric based on the following:

Bandwidth: The slowest link in the path.
Delay: Cumulative delay of the path.
Load: The traffic utilization on the link.
Reliability: The error rate of the link.

The formula to calculate the EIGRP metric is:

Metric=256×(10 *7/Bandwidth + Delay)

# 5. EIGRP Packet Types
### EIGRP uses five packet types:

#### 1. Hello packets: Used for neighbor discovery and to maintain adjacencies.
#### 2. Update packets: Used to send routing updates.
#### 3. Query packets: Sent when a router needs to find a new route.
#### 4. Reply packets: Responses to query packets.
#### 5. ACK packets: Acknowledgment for reliable delivery.

# 6. Configuration of EIGRP on Cisco Routers
## Basic EIGRP configuration on Cisco routers involves:
### Router(config)# router eigrp 1
### Router(config-router)# network 192.168.1.0 0.0.0.255
### Router(config-router)# no auto-summary
### Router(config-router)# end
Here, 1 represents the Autonomous System (AS) number, and 192.168.1.0 is the network to advertise.

# 7. Advanced EIGRP Concepts 
#### Feasible Successor: Backup routes stored in the topology table.
#### DUAL Algorithm: Used to ensure loop-free paths and rapid convergence.

# 8. Troubleshooting EIGRP
### Common commands for troubleshooting:

#### show ip eigrp neighbors
#### show ip eigrp topology
#### debug eigrp packets

# 9. Conclusion
### EIGRP provides a scalable, efficient, and rapid solution for dynamic routing. While it was Cisco-proprietary, it has now become more widely supported on other platforms, making it an essential tool for network administrators.






