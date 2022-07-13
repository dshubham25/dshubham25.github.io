---
layout: post
title: Computer Networks Notes
category: Core Subjects
excerpt: Guide on hosting a Jekyll site with custom domain on Github Pages.
redirect_from: /2022/07/13/Computer-Networks-Notes/
---

In this blog post I am going to write about Computer Networks topics and some of the frequently ask questions on Computer Networks.

### What is Computer Networks?

Computer Networks is defined as the connection of computer devices that can exchange the data and share resources with each other. These connections with proper protocols is called communication.
Protocol helps in understanding the messages.

When a process communicates with another process in the same machine it is called **inter-process communication (IPC)**.

#### OSI Model

OSI Models are considered to be the theoretical models, because of their functionalities.

There are 7 layers in the OSI Model. These are:

<p align="center">
  <img src="https://miro.medium.com/max/1024/1*17Zz6v0HWIzgiOzQYmO6lA.jpeg" alt="OSI Model" style="height: 400px; width:800px;" class="center">
</p>

#### TCP/IP Model

TCP/IP Model is defined as the practical version of the OSI model, it was built by ARPANET. TCP/IP model supports Client to Server or Peer to Peer connection. There are 4 layers of the TCP/IP Model and these are:
1. Application Layer
2. Transport Layer
3. Internet Layer
4. Network Acess Layer

<p align="center">
    <img src="https://media.geeksforgeeks.org/wp-content/uploads/tcpAndOSI.png" alt="TCP/IP Model" style="height: 400px; width:800px;"/>
</p>

### Physical Layer

Physical layer is the last layer in the OSI Model layers and physical layer deals with the hardwares.

- Cables, Signals
- Cables and Connectors
- Physical Topologies
- Hubs and Repeaters

*Multiplex and Demultiplexing*

Multiplexer refers to a type of combinational circuit that accepts multiple inputs of data but provides only a single output. The demultiplexer refers to the type of combinational circuit that accepts just a single input but directs it through multiple outputs. A Multiplexer performs conversion from parallel to serial.

### Data Link Layer

Data link layer is the second last layer and it takes data from the Network layer and provides data to the physical layer.

Data Link Layer works within a network.
They are also known as Hop to Hop delivery or Node to Node delivery.

Few of the functionalities of data link layer is 
- Flow Control : Basically means at what speed the message needs to be sent. DLL controls the flow of each node or Hop.

    - Stop & Wait Protocol
    - Go-Back-N 
    - Selective Repeat

- Error Control : It is better to check the error at each node rather than checking the error at the destination of the message sent. DLL error control happens at Node to Node.

    - CRC
    - CheckSum

In data link layer, the packets gets divided into fixed size frames.

 | Header | Frames | Tail | - > to ensure that the data reaches properly to the next node.

### Network Layer

It takes data from the transport layer and transfers it back to data link layer. It is host to host/ Source to Destination/ Machine to Machine type of connection.
This type of connection in Network layer is performed using ==IP Address==.
- Logical Address(IP Address) is basically Network ID and Host ID.
- Routing : When message reaches from Source to R1(Router 1) - Router 1 decides how to send the data to the destination.(normally using shortest path).
- Fragmentation : When packets goes from one place to another. -> Fragmentation is used.

### IP Addressing

IP Addressing is basically is classified into 5 classes.

**Class A** : In Class A the 32-bit IP Address gets divided into 4 octets(8 bits) and the first octet is known as Network ID. To classify it as the Class A IP Address. The 1^st^ bit of the network ID is fixed (0).

- 2^31^ -- # IP Address possible in Class A.
- Range of Class A = (0-127)
- 2^7^ -- # N/W in Class A possible: 
    - 2^7^ = 128
    - [00000000] and [11111111] are not given to anyone so - 128-2 = 126 N/W is given.
- 2^24^ -- # host possible in every N/W
- Default mask of Class A is 255.0.0.0

**Class B** : In Class B, the first 2 bits of the 1^st^ octet is fixed (10). first two octets are network id and remaining as host id.
- 2^14^ -- # of network possible
- Range of Class B = (128-191)
- 2^30^ -- # of Address
- 2^16^ - 2 = 65534 -- # of host possibe in each network.
- Default mask of Class B is 255.255.0.0

**Class C** : In Class C, the first 3 bits of 1^st^ octet is fixed(110). first 3 octets are of network id and remaining is host id.
- 2^29^ -- # of IP address.
- Range of Class C = (192-223)
- 2^21^ -- # of n/w.
- 2^8^ - 2 = 254 -- # of host possible in each n/w.
- Default mask of Class C is 255.255.255.0

**Class D** : In Class D, the first 4 bits of 1^st^ octet is fixed(1110). There is no N/W ID or Host ID.
- 2^28^ -- # of IP address
- Range of Class D = (224-239)
- Class D is reserved for multicasting or group broadcasting or group emailing.

**Class E** : In Class E, the first 4 bits of 1^st^ octet is fixed(1111). There is no N/W ID or Host ID.
- 2^28^ -- # of IP address
- Range of Class E = (240-255)
- Class E is reserved for military purpose.

<p align="center">
    <img src="https://techhub.hpe.com/eginfolib/networking/docs/switches/3100v2/5998-5992s_l3-ip-svcs_cg/content/images/image5.png" alt="IP Addressing"/>
</p>

### Transport Layer

Transport layer is used for End to End Delivery / Port to Port Delivery
In Transport Layer there is basically two protocols ==TCP and UDP==

#### TCP(Transmission Control Protocol)
- It is a connection-oriented protocol.
- TCP has built-in systems to check for errors and to guarantee data will be delivered in the order it was sent.
- No loss of data.
- Whenever data is send through TCP, TCP adds header along with the data.

Byte Streaming : TCP is a byte streaming protocol -> from application layer continous data comes without any limitation.
TCP -> Bytes -> Segments(TCP converts each data into segments and each segment has many bytes).

<p align="center">
    <img src="https://www.lifewire.com/thmb/OhU9Rn5-Myfpbzjyy98U8UMAMCs=/1235x695/smart/filters:no_upscale()/tcp-headers-f2c0881ea4c94e919794b7c0677ab90a.jpg" alt="TCP Header"/>
</p>

#### UDP(User Datagram Protocol)
- It is a connectionless Internet protocol.
- there is no overhead for opening a connection, maintaining a connection, or terminating a connection; data is continuously sent to the recipient, whether or not they receive it. 
- Loss of data can occur.
- No built-in system to check for errors.
- Faster protocol as compared to TCP.
<p align="center">
    <img src="https://www.gatevidyalay.com/wp-content/uploads/2018/10/UDP-Header.png" alt="UDP Header"/>
</p>


#### TCP VS UDP
<p align="center">
    <img src="http://www.homenethowto.com/wp-content/uploads/table-tcp-udp.png" alt="TCP vs UDP" style="height: 400px; width:800px;"/>
</p>

### Session Layer
The main work of Session layer is the starting of the session, authorization and authentication.
Authorization is basically a set of priviledges.
In session layer, Session Restoration can be done(basically it acts like a checkpoint).

### Presentation Layer
In presentation layer, Code conversion is basically done.
- Code Conversion means that format the data according to the machine.
Encryption/ Decryption is also done in presentation layer.

### Application Layer

| Protocol Name | Port no. | Transport Protocol|
| ----------- | ----------- | ----------- |
| Echo | 7 | TCP/UDP|
| FTP(file transfer protocol) | 20/21 | TCP |
| SSH | 22 | TCP |
| Telnet | 23 | TCP |
| SMTP | 25 | TCP | 
| DNS | 53 | UDP |
| DHCP(Dynamic Host Control Port) | 67 / 68 | UDP | 
| TFTP(Trivial File Transfer Protocol) | 69 | UDP | 
| HTTP | 80 | TCP |
| HTTPS | 443 | TCP |
| POP | 110 | TCP |
| NTP | 123 | UDP |
| RIP | 520 | UDP |

