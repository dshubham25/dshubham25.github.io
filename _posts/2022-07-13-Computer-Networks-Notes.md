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

**Class A** : In Class A the 32-bit IP Address gets divided into 4 octets(8 bits) and the first octet is known as Network ID. To classify it as the Class A IP Address. The 1<sup>st</sup> bit of the network ID is fixed (0).

- 2<sup>31</sup> -- # IP Address possible in Class A.
- Range of Class A = (0-127)
- 2<sup>7</sup> -- # N/W in Class A possible: 
    - 2<sup>7</sup> = 128
    - [00000000] and [11111111] are not given to anyone so - 128-2 = 126 N/W is given.
- 2<sup>24</sup> -- # host possible in every N/W
- Default mask of Class A is 255.0.0.0

**Class B** : In Class B, the first 2 bits of the 1<sup>st</sup> octet is fixed (10). first two octets are network id and remaining as host id.
- 2<sup>14</sup> -- # of network possible
- Range of Class B = (128-191)
- 2<sup>30</sup> -- # of Address
- 2<sup>16</sup> - 2 = 65534 -- # of host possibe in each network.
- Default mask of Class B is 255.255.0.0

**Class C** : In Class C, the first 3 bits of 1<sup>st</sup> octet is fixed(110). first 3 octets are of network id and remaining is host id.
- 2<sup>29</sup> -- # of IP address.
- Range of Class C = (192-223)
- 2<sup>21</sup> -- # of n/w.
- 2<sup>8</sup> - 2 = 254 -- # of host possible in each n/w.
- Default mask of Class C is 255.255.255.0

**Class D** : In Class D, the first 4 bits of 1<sup>st</sup> octet is fixed(1110). There is no N/W ID or Host ID.
- 2<sup>28</sup> -- # of IP address
- Range of Class D = (224-239)
- Class D is reserved for multicasting or group broadcasting or group emailing.

**Class E** : In Class E, the first 4 bits of 1<sup>st</sup> octet is fixed(1111). There is no N/W ID or Host ID.
- 2<sup>28</sup> -- # of IP address
- Range of Class E = (240-255)
- Class E is reserved for military purpose.

<p align="center">
    <img src="https://techhub.hpe.com/eginfolib/networking/docs/switches/3100v2/5998-5992s_l3-ip-svcs_cg/content/images/image5.png" alt="IP Addressing"/>
</p>

### IPv4 vs IPv6

<p align="center">
    <img src="https://www.researchgate.net/profile/Ashad-Qureshi/publication/339722884/figure/fig4/AS:865754383650819@1583423338631/Brief-comparison-of-IPv4-and-IPv6.png" alt="IPv4 and IPv6"/>
</p>


### Transport Layer

Transport layer is used for End to End Delivery / Port to Port Delivery
In Transport Layer there is basically two protocols (TCP and UDP)

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


### Domain Name Server(DNS)

Domain Name Server maps DNS to IP address. IP address can change but DNS should not. DNS translates domain names to IP addresses so browsers can load Internet resources. The process of DNS resolution involves converting a hostname (such as www.example.com) into a computer-friendly IP address (such as 192.168.1.1). An IP address is given to each device on the Internet, and that address is necessary to find the appropriate Internet device - like a street address is used to find a particular home. When a user wants to load a webpage, a translation must occur between what a user types into their web browser (example.com) and the machine-friendly address necessary to locate the example.com webpage.

### 3-Way Handshaking

A three-way handshake is a 3 step process that TCP/IP networks use to establish a secure and reliable connection between sender(client) and receiver(server).

A three-way handshake includes the following steps:
1. SYN
- To establish a connection, the client sends an SYN (Synchronize Sequence Number) request to the server.
- The request message contains information like the initial sequence number, maximum segment size,  window size, SYN bit set to 1, and ACK bit set to 0. 
- The client then awaits a response from the server.

2. SYN+ACK
- The server answers with an SYN-ACK message after receiving the client’s request.
- In the response, both ACK and SYN  bits are set to 1 indicating the server has acknowledged the request and wishes to establish a connection with the client.
- The server also sends a random sequence number, window size, maximum segment size, and ACK’s acknowledgment number(which is the client’s received sequence number+1).

3. ACK
- The client sends an acknowledgment(ACK) to the server after receiving SYN-ACK from the server.
- The client sets the ACK bit to 1 and sends it to the server along with an acknowledgment number (which is the server’s SYN sequence number +1) and also sets the SYN bit to 0.
- After this procedure is completed, the client and server establish a connection through which they will begin the data transfer.

<p align="center">
    <img src="https://takeuforward.org/wp-content/uploads/2022/05/image-1.png" alt="3-way handshaking"/>
</p>

### Socket Programming

It is a way on how application will be communicating with each other over the internet.
Socket is a node or end point connection. Data will be generated by some application in application layer and it will send to the application layer of other node.

<p align="center">
    <img src="https://media.geeksforgeeks.org/wp-content/uploads/Socket_server-1.png" alt="Socket server"/>
</p>


### What happens when you type a URL/(www.google.com)?

1. First thing that happens is that your browser looks up in its cache to see if that website was visited before and the IP address is known.
2. If it can’t find the IP address for the URL requested then it asks your operating system to locate the website. The first place your operating system is going to check for the address of the URL you specified is in the host file. If the URL is not found inside this file, then the OS will make a DNS request to find the IP Address of the web page.
3. The first step is to ask the Resolver (or Internet Service Provider) server to look up its cache to see if it knows the IP Address, if the Resolver does not know then it asks the root server to ask the .COM TLD (Top Level Domain) server – if your URL ends in .net then the TLD server would be .NET and so on – the TLD server will again check in its cache to see if the requested IP Address is there. 
4. If not, then it will have at least one of the authoritative name servers associated with that URL, and after going to the Name Server, it will return the IP Address associated with your URL.
5. After the OS has the IP Address and gives it to the browser, it then makes a GET (a type of HTTP Method) to said IP Address. When the request is made the browser again makes the request to the OS which then, in turn, packs the request in the TCP traffic protocol we discussed earlier, and it is sent to the IP Address. 
6. On its way, it is checked by both the OS’ and the server’s firewall to make sure that there are no security violations. And upon receiving the request the server (usually a load balancer that directs traffic to all available servers for that website) sends a response with the IP Address of the chosen server along with the SSL (Secure Sockets Layer) certificate to initiate a secure session (HTTPS). 
7. Finally, the chosen server then sends the HTML, CSS, and Javascript files (If any) back to the OS who in turn gives it to the browser to interpret it. And then you get your website as you know it.

