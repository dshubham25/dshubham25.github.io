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
  <img src="https://miro.medium.com/max/1024/1*17Zz6v0HWIzgiOzQYmO6lA.jpeg" alt="OSI Model" style="height: 500px; width:900px;" class="center">
</p>

#### TCP/IP Model

TCP/IP Model is defined as the practical version of the OSI model, it was built by ARPANET. TCP/IP model supports Client to Server or Peer to Peer connection. There are 4 layers of the TCP/IP Model and these are:
1. Application Layer
2. Transport Layer
3. Internet Layer
4. Network Acess Layer

<p align="center">
    <img src="https://media.geeksforgeeks.org/wp-content/uploads/tcpAndOSI.png" alt="TCP/IP Model" style="height: 500px; width:900px;"/>
</p>

### Physical Layer

Physical layer is the last layer in the OSI Model layers and physical layer deals with the hardwares.

- Cables, Signals
- Cables and Connectors
- Physical Topologies
- Hubs and Repeaters

*Multiplex and Demultiplexing*

Multiplexer refers to a type of combinational circuit that accepts multiple inputs of data but provides only a single output. The demultiplexer refers to the type of combinational circuit that accepts just a single input but directs it through multiple outputs. A Multiplexer performs conversion from parallel to serial.

#### Data Link Layer

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

#### Network Layer