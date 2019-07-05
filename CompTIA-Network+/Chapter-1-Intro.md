# Introduction to Networks

## What is a Network

### The Local Area Network (LAN)

* Usually restricted to spanning a particular geographic location like office or home.
* A big LAN can be split into logical zones known as **workgroups**.
* A **router** can connect to different LANs together so clients from  different LANs can connect with each other.

## Common Network Components

* Workstations
  * Often seriously powerful computers that run more than one CPU and whose resources are available to other users on the network to access when needed.
* Servers
  * Also powerful computers and can be known as the network operating system. (File server, Mail server, Web server, Fax server, Proxy server, etc.)
* Hosts
  * Could be referring to almost  any type of network devices, including workstations and servers.
  * TCP/IP speaking, a host mean any network device with an IP address.

### Virtual LANs (VLANs)

* A VLAN is a LAN that it is not physically built. And you don’t have to be in the same geographic location to be connected.
* Using a particular port  that is configured for the LAN workgroup you are a member of -> VLAN membership, and it’s got to be configured on a network device called switch.
* VLANs are new workgroups.

### Wide Area Network (WAN)

WAN network are what we use to span large geographic areas and truly go distance. Like Internet, WANs usually employ both routers and public links.

The Internet is a prime example of what’s known as a distributed WAN.

### Virtual Private Networks (VPNs)

A typical WAN connects two or more remote LANs together using someone else’s network, such as your ISP, using a router.

Your local host and router see these networks as remote networks and not as local networks or local resources.

A VPN actually makes your local host part of the remote network by using the WAN link that connects you to the remote LAN.

The VPN will make your host appear as through it is actually local on the remote network.

### Network Architectures: P2P or C/S

#### Peer-to-Peer Networks

Do not have any central or special authority, and computers are all peers.

Computers existing in a peer-to-peer network can be client machine that access resources and server machines that provide them to other computers.

#### Client/Server Networks

A Single Server is specified that uses a network operation system for managing the whole network.

## Physical Network Topologies

### Bus Topology

Bus Topology consists of two distinct and terminated ends, with each of its computers connecting to one unbroken cable running its entire length.

Pro:

* Easy to install
* Inexpensive

Con:

* hard to troubleshoot
* hard to move, change
* does not offer fault tolerance (single cable)

### Start Topology

Star topology’s computers are connected to a central point with their own independent cable or wireless connections. Central spot inhabited by a device such as hub, switch or an access point.

Pro:

* Connected to the central device individually
* More fault tolerance and easier to troubleshoot
* More scalable

Con:

* expensive
* It has a single point of failure (central device)

### Ring Topology

Outdated topology.

### Mesh Topology

Complicated to manage
Rarely used today

### Point-to-Point Topology

Direct connection between two routers, giving you one communication path.

Usually within many of today’s WANs

### Point-to-Multipoint Topology

Usually in routers

### Hybrid Topology

A combination of two or more types of physical  or logical topples within the same network.

## Topology Selection, Backbones, and Segments

* Cost
* Ease of Installation
* Ease of Maintenance
* Fault-Tolerance Requirement

Backbone vs. Segment
