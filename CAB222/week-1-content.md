# Week 1 Content
weeks 1's content surrounds the history of the internet and the basics of the internet.
> I am not going through the history portion i do not care

## internet termniology and basics
>a decent chunk of this week is just terminology

|  Term  |  description  |
|-----|-----|
| LAN | Local Area Network, the lowest level of connection (think within the same network) |
| WAN | Wide Area Network, standard communication for carrying network traffic between locatoins |
| MAN | Metropolitan area networks, uses WAN tech to connect LANS within a geographic region (country, city etc) |
| Internetwork | a collection of LANS tied together by a device (eg router) |
| Internet | worldwide public internetwork, uses tcip/ip and http(s) |
| Intranet | a private internetwork only available to users connected to the network |
| Extranet | like an internetwork however it can be viewed by ean esxternal user |
| Packets | A chunk of data setn across a network |
| NIC | Network interface controller, essentially a wifi card, or router. |
| MAC Address | Media control access adress, a unique identifier that is assigned to a NIC |
| Frame | a frame is what a packet is placed into, the fram contains the source information and the destination MAC Address |
| Bit | 1 and 0, the individual binary elements that make up a byte |

## fundamentals of network communication
a computer netowrk requires at least 2 computers connected via some kind of transmission medium
- like an ethernet cable or via airwaves that are transmitted
- they then need to be connected to an interconnected device
  - router
  - switch
  - access points

### layers of the network communcation process
there are 4 steps to go through before reaching the network medium:
![communication layers](https://github.com/shambp/QUT-IT-Study-Guide/blob/main/CAB222/week-1-images/Capture.PNG)
> Taken directly from the powerpoint
after it goes through all of these layers it can go through the network medium and then through to the receiving machine.

## Network Architecture
the design of a communication network and is a framework that follows some specifications.

To quote the powerpoint
>it is a framework for the specification of.
>>
> A networks's physical components and their functional organization and configuration, its operational principles and procedures, as well as data formats use.

THere are two reference models. Those being the TCP/IP protocol suite and the OSI (open system interconnectoin) model.
> see the layers heading for more info

### OSI reference model
The OSI was proposed by the ISO and provides a common framework for users to work from. It is non specific and is easily applied to most networking protocols.

The osi model is a seven layer organizaion of how data travels. With each layer providing services to the next layer until it reaches the application layer.

### Encapsulation
encapsulation is the addition of control information to a data uit as it moves through the internet layers. Think of it like putting an item inside of a box ready to send off, with the sender and the receivers name & address, they are merely information to help the packet move to its destination. The opposite of encapsulation is de-encapsulation. 
### The layers
![Structure of the models](https://github.com/shambp/QUT-IT-Study-Guide/blob/main/CAB222/week-1-images/Capture2.PNG)
>Taken from the powerpoint
>
> The layers are numbered from 7-1 starting with the application layer
#### Applicaton Layer
the application layer provides interfaces. File sharing, message handling and database access.
> protocols like HTTP and SMTP are found on the application layer

#### Presentation Layer
handles formatting and translation, which can either be converting data into a format that was specified within the application layer, or reversing the conversion depending on if you are sending or receiving information.

Encryption/decryption also happens at this layer

#### Session Layer
This layer handles communication setup and permits two computers to hold ongoing communcations (a session).

#### Transport Layer
manages data transfer by breaking down data into smaller chunks called segments.

Segmenting data is important as every network as a maximum transmission unit (MTU). This layer also includes flow control + acknowledgements to ensure reliability.

#### Network Layer
performs logical addressing,
maps between logical network addresses and performs routing.

The IP proctocol is on this layer

#### Data-Link Layer
Is the buffer between network and physical layer, works with frames to define the mac address. This step is usually handled by the NIC.

#### Physical Layer
The final layer, converts bits into signals for outgoing messages and the inverse for incoming. Things like encoding happens at this layer

![OSI model summary](https://github.com/shambp/QUT-IT-Study-Guide/blob/main/CAB222/week-1-images/Capture3.PNG)
>Taken from the powerpoint

# week 1 over