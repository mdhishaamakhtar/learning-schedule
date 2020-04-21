<h1 align=center>Network and Communication</h1>

## Types of Data Flow

- Simplex
- Half Duplex
- Full Duplex

## Elements of a Protocol

- Message encoding
- Message formatting and encapsulation
- Message timing
- Message size
- Message delivery options

### Message delivery options

- Unicast
- Multicast
- Broadcast

## Peer to Peer Network

- No centralized administration
- All peers are equal
- Simple sharing applications
- Not scalable

## Client Server Network

- Centralized Administration
- Req-Res Model
- Scalable
- Server may be overloaded

### Wired Media

- Ethernet straight-through cable(different kinds of devices)
- Ethernet crossover cable(same devices)
- Fiber Optic Cable
- Coaxial Cable(set top box)
- USB Cable(Universal Serial Bus)

### Wireless Media

- Infrared Waves(short range like TV remote)
- Radio Waves(Bluetooth,WiFi)
- Microwaves(Cellular System)
- Satellite(Longe Range like GPS)

### Services

- e-Mail
- Storage Services
- File Sharing
- Instant Messaging
- Online Game
- Voice over IP
- Video telephony
- World Wide Web

## Types of Computer Networks

- Local Area Network(LAN)
- Metropolitian Area Network(MAN)
- Wide Area Network(WAN)
- The Internet

## Types of Network Topology

- Physical Topology
- Logical Topology

##### Bus

- All Data transmitted between nodes in the network s transmitted over a common transmission medium and is able to be received by all nodes in the network simultaneously
- A signal containing the address of the intended receiving machine travels from a source machine in both directions to all machines connected to the bus until it finds its intended recipient

* Advantages
  - Less expensive
  - Suited for temporary network
  - Node failures does not affect others
* Disadvantages
  - Not fault tolerant
  - Limited Cable length
  - No security

##### Star

- Every node is connected to a central node called hub or switch
- Centralized management
- All traffic must pass through Hub or Switch

* Advantages
  - Easy to design and implement
  - Centralized administration
  - Scalable
* Disadvantages
  - Single point of failure affects the entire network
  - Bottlenecks due to overloaded switch/Hub
  - Increased cost due to switch/hub

##### Ring

- A ring topology is a bus topology in a cosed loop
- Peer to Peer LAN technology
- Two connections: one to each of its nearest neighbours
- Unidirectional
- Sending and receiving data takes place with the help of a token

* Advantages
  - Performance better than bus topology
  - All nodes with equal access
* Disadvantages
  - Unidirectional: Single point of failure will affect the whole network
  - Can cause bottleneck due to weak links
  - More the load, less the performance
  - No security

##### Mesh

- Each node is directly connected to every other node in the network
- Fault tolerant and reliable

* Advantages
  - Fault tolerant
  - Reliable
* Disadvantages
  - Issues with broadcasting
  - Expensive and impractical for a large network

##### Hybrid

- Combination of one or more different topologies

## IP Address

- It changes based on location of the computer
- Depends on which Local Area Network a computer is connected to
- It is router friendly
- Internet Protocol is the full form
- Two types IPv4 and IPv6
- IPv4 is between 0.0.0.0 and 255.255.255.255(3 bits)

## MAC Address

- MAC stands for Media Access Control
- Every node in the LAN is identified with it
- Physical address or Hardware Address
- Unique for every computer and cannot be changed. Location independent
- Assigned by the manufacturer
- Represented in hexadecimal for example 70-20-84-00-ED-FC and the separator is decided by the manufacturers such as (-),(.) and (:)

| IP Address               | MAC Address                |
| :----------------------- | :------------------------- |
| Needed for communication | Needed for Communication   |
| 32 Bits                  | 48 Bits                    |
| Represented in decimal   | Represented in hexadecimal |
| Router needs IP Address  | Switch needs MAC Address   |
| Ex: 10.10.23.56          | Ex: 70-20-84-00-ED-FC      |

## Port Addressing

- **Let us take an analogy to consider understand this: Suppose something has to be delivered from one city to another. First the package has to reach the destination city. Then the apartment of the receiver and then go to the flat of the correct user.**
- Similarly, IP Address can be compared to the IP Address i.e. the **IP Address** gives the **location** of the computer
- With the **MAC address**, we can pinpoint a computer connected to the LAN of the same IP Address i.e. reaching the correct Apartment
- And then comes **PORT** from which the **correct process** can be identified. Just like reaching the right person in that apartment
- In a node, many processes will be running
- Data which are sent/received must reach the right process
- Every process in a node is uniquely identified using port numbers
- **PORT = Communication Endpoint**
- Fixed and Dynamic Port Number(between 0 - 65535)

## Switching in Computer Networks

- Switching in computer networks helps in deciding the route for data transmission if there are multiple paths in a larger network
- One to One Connection

#### Switching Techniques

- Circuit Switching
- Message Switching
- Packet Switching
  - Datagram Approach
  - Virtual Circuit Approach

#### Circuit Switching

- A dedicated path established between sender and receiver
- Before data transfer, connection is established first
- 3 Phases in circuit switching
  - Connection Establishment
  - Data Transfer
  - Disconnection

#### Message Switching

- Store and forward Mechanism
- Message is transferred as a complete unit and forwarded using store and forward mechanism at the intermediary node
- Not suited for streaming media and real time applications

#### Packet Switching

- The internet is a packet switching network
- Message is broken into individual chunks called packets
- Each packet is sent individually
- Each packet will have source and destination IP Address sequence number
- Sequence numbers will help receiver to:
  - Reorder the packets
  - Detect Missing Packets
  - Send Acknowledgements

##### 1) Datagram Approach

- It is also known as connection-less switching
- Each independent entity is called datagram
- Datagrams contain destination information and the intermediary devices uses this information to forward datagrams to right destination
- In this approach, the path is not fixed
- Intermediate nodes take the routing decisions to forward the packets

##### 2) Virtual Circuit Approach

- It is also known as connection-oriented switching
- In the case of Virtual circuit switching, a preplanned route is established before
- Call request and call accept packets are used to establish the connection between sender and receiver
- In this approach, the path is fixed for the duration of a logical connection
