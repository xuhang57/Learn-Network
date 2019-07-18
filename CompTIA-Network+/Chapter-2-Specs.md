# The Open Systems Interconnections Specifications

## Inter-Networking Model

### The layered approach

A reference model is a conceptual blueprint of how communications should take place.

Advantages of Reference Models:

* It divides the network communication process into smaller and simpler components, thus aiding component development, design, and troubleshooting.
* It allows multiple-vendor development through standardization of network components.
* It allows various types of network hardware and software to communicate
* It encourages industry standardization be defining what functions occur at each layer of the model.
* It prevents changes in one layer from affecting other layers, so it doesn’t hamper development and makes application programming easier.

## The OSI Reference Model

* Application Layer (7)
  * file, print, message, database, and application services
  * provide a user interface
* Presentation Layer (6)
  * data encryption, compression, and translation services
  * present data, handles processing such as encryption
* Session Layer (5)
  * dialog control
  * keeps different applications data separate
* Transport Layer (4)
  * end-to-end connection
  * provides reliable or unreliable delivery
  * performs error correction before retransmit
* Network Layer (3)
  * routing
  * provides logical addressing, which routers use for path determination
* Data Link Layer (2)
  * framing
  * combines packets into bytes and bytes into frames
  * provides access to media using MAC address
  * performs error detection not correction
* Physical Layer (1)
  * physical topology
  * moves bits between devices
  * specifies voltage, wire speed, and pin-out of cables

The top three layers define how the applications within the end stations will communicate with each other and with users.

The bottom four layers define how data is transmitted end to end.

### The Application Layer

The Application layer of the OSI model marks the spot where users actually communicate to the computer.

The Application layer is also responsible for identifying and establishing the availability of the intended communication partner and determining whether sufficient resources for the intended communication exist.

Application layer acts as an interface between application programs, such as FTP, TFTP

### The Presentation Layer

The Presentation layer gets its name from its purpose: It presents data to the Application layer and is responsible for data translation and code formatting.

It is a translator and provides coding and conversion functions. By providing translation services, the Presentation layer ensures that data transferred from one system’s Application layer can be read by the Application layer of another one.

Tasks like data compression, decompression, encryption, and decryption are associated with this layer.

### The Session Layer

The Session layer is responsible for setting up, managing, and then tear down sessions between Presentation-layer entities.

It also provides dialogue control between devices, or nodes. It coordinates communication between systems and serves to organize their communication by offering three different modes: simplex, half duplex, and full duplex.

Basically, it keeps applications’ data separate from other applications’ data.

### The Transport Layer

The Transport layer segments and reassembles data into a data stream. Services located in the Transport layer segment and reassemble data from upper-layer applications and unite it onto the same data stream.

It is responsible for providing mechanisms for multiplexing upper-layer applications, establishing sessions, and tearing down virtual circuits. It also hides details of any network-dependent information from the higher layers by providing transparent data transfer.

The Transport layer can be connection-less or connection-oriented.

Connection-Oriented Communication:

Before a transmitting host starts to send segments down the model, the sender’s TCP process contacts destination’s TCP process to establish a connection. What is created is known as a virtual circuit. For example, three-way handshakes.

Three-way handshake

* SYN
* SYN-ACK
* SYN

Flow Control

Data integrity is ensured at the Transport layer by maintaining flow control and by allowing users to request reliable data transport between systems.

Flow control provides a means for the receiver to govern the amount of data sent by the sender.

When a machine receives a flood of datagrams too quickly for it to process, it stores them in a memory section called a buffer.  And there is a network flood-control systems, which issues “not ready” indictor to the sender, or source, of the flood.

Therefore, a service is considered connection-oriented if it has the following characteristics:

* A virtual circuit is set up (such as three-way handshake)
* It uses sequencing
* it uses acknowledgements
* it uses flow control

Windowing

Ideally, data throughput happens quickly and efficiently. The quantity of data segments (measured in bytes) that the transmitting machine is allowed to send without receiving an acknowledgment for them is called a window.

Acknowledgement

Positive acknowledgment with retransmission is a technique that requires a receiving machine to communicate with the transmitting source by sending an acknowledgment message back to the sender when it receives data.

The Transport layer doesn’t need to use a connection-oriented service. For example, there is TCP and UDP.

### The Network Layer

The Network layer manages device addressing, tracks the location of devices on the network, and determines the beltway to move data, which means that the Network layer must transport traffic between devices that are not locally attached.

Routers (layer 3 devices) are specified at the Network layer and provide the routing service within an internetwork.

Two types of packets are used at Network layer:

* Data packets
  * These are used to transport user data through the internetwork.
  * Protocol used to support data traffic are called routed protocols such as IP.
* Route-update packets
  * These are used to update neighboring routers about the networks connected to all routers within the internetwork.
  * Routing Information Protocol (RIP), Enhanced Interior Gateway Routing Protocol (EIGRP), and Open Shortest Path First (OSPF)

* Network Address
* Interface
* Metric

### The Data Link Layer

The Data Link layer provides the physical transmission of the data and handles error notification, network topology, and flow control.

It ensures that messages are delivered to the proper device on a LAN using hardware addresses, and translates messages from the Network Layer Ito bits for the Physical layer to transmit.

It formats the message into different pieces, such as data frames.

The IEEE Ethernet Data Link layer has two sub-layers:

* Media Access Control (MAC)
  * Defines how packets are placed on the media. “First come first served” access where everyone shares the same bandwidth.
* Logical Link Control (LLC)
  * Responsible for identifying Network-layer protocols and encapsulating them. It tells the Data Link layer what to do with a packet once a frame is received.

### The Physical Layer

The Physical Layer sends bits and receives bits. It specifies the electrical, mechanical, procedural, and functional requirements for activating, maintaining, and deactivating a physical link between end systems. 

It is also where you identify the interface between the data terminal equipment (DTE) and the data communication equipment (DCE).

## Introduction to Encapsulation

When a host transmits data across a network to another device, the data goes through encapsulation: It’s wrapped with protocol information at each layer of the OSI model.

At a transmitting device, the data-encapsulation method works like this:

1. User information is converted to data for transmission on the network
2. Data is converted to segments, and a reliable connection is setup between transmitting and receiving hosts
3. Segments are converted to packets or datagrams, and a logical address is placed in the header so each packet can be routed thought a internetwork.
4. Packets or datagrams are converted to frames for transmission on the local network. Hardware (Ethernet) addresses are used to uniquely identify hosts on a local network segment.
5. Frames are converted to bits, and a digital encoding and clocking scheme is used.
