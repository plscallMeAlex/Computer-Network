## Line Configuration
- Point to point if want to connect simple CPE wireless setup on the rooftop of each building use link to connect.
- Multipoint (Most use) get the fastest but if you have enough money. We must have a traffic rule.

**Network Topology** (Gonna Show in Exam) (How connect.)
- **Mesh Topology** - Provide point to point link to every point (one point to every point). Get a full speed don't need a traffic maximum performance. If small is ok but if a large system it cost a lot.
- **Star Topology** - Having a centralize system like (using nowadays) switch or hub. Each device gonna go to hub calling dedicated link. It will send the data to switch and it will forward data out.
- **Tree (Hierarchy) Topology** - We have a root switch and child can be a switch or computer but leaves will be switch. Like a star but it extended start.
- **Bus  Topology** - We have dedicated link almost off see. Have one line connect the device and trap to the bus. It not unreliable if cut the line the whole network is gone like during adding the new device network will down.
- **Ring Topology** - One connect to forward one connect to backward and connect like a ring. If some line are break off the whole network will down.
- Wireless - The household communication.

**Transmission Mode** (Technique to sending the data) must know.
- Simplex - One way communication it will have sending and receiver like a radio center sender will always a sender receiver always a receiver.
- Half-Duplex - Walky-Talky system one can be a sender and receiver but not a same time like push button to change the mode if be a same the network might loss.
- Full-Duplex - Two ways communication can be sender and receiver at the same time.

**Categories of Networks**
It group like LAN and Internet but in LAN will separate how can it be to LAN, MAN, WAN.
- LAN
- Internet
Bluetooth slower and short but save the device battery but need more bandwidth.
Wireless cost the power consumption but range is far than the Bluetooth.

**Wireless Networks**
- Normal ieee802.11

Connection-Oriented and connectionless Service.
- Connection-oriented service - We need connection setup first. Establishes a connection like setup circuit to from one line to another line (or path to the end) we use this path to send data once release connection will drop.
- Connectionless service - Fast but unreliable communicate without the connection like a sending a post and let the post-office do the rest but need the specific address it may loss and we don't know it sent to where.
Internet layer is full duplex.
Using IP on top with TCP or (UDP is connectionless).
If want the speed we need to sacrifice some bit use UDP to send data.

Protocol - meaning set of languages 
## Protocol Hierarchy
Like if want to communicated to another person like manager talk to manager during the process it will have a translator between line to standard languages that understand both of translator and send the message to secretary () and it will send message to another company and another company will receive and send to translator and send a translated data to manager everyone have there own jobs. 
In the network use the same OSI models.

## Function Layers
	Depends on the each focus on one main responsibility.
- **Physical Layer** - The lowest layer (cable). Main is bit transmission or line configuration. Talk about transmission mode have to select what gonna use and Signal like if use LAN use copper or something, wireless what frequency (Voltage, Light, Frequency). Encoding use 10 to represent 1 use 01 to represent 0 why don't use binary encoding Manchester encoding because if sending 1111 through the line and change to 0 u will charge a lot of voltage and u want to discharge it will electric shock and long time to discharge might damage the devices. Interface. Media CAT is a LAN line media.
- **Data Link Layer** - Main is node to node deliver send data from device to another device like device to switch. **Addressing** physical address and MAC address. Physical Address the last 24 bit will represent the device. **Access control** is how we gonna access the media and control the media and send the data through the media need to setup the rules. **Flow control** if the sender send the bit speed of more than the receiver can receive it will try to make the sender and receiver to have the same speed it will have protocol to tell too fast package loss. **Error control** how we detected or control the error. **Synchronization** technique to send $\delta$T to measure timing of the signal receive. The data will Be SOF and next will be Address, S-MAC, Data, ErrorControlSequence. Use SOF to calculate $\delta$T for the rest of data. In this line called frame. 
- **Network Layer** - Main is source to destination delivery is from the computer to another device it might contain a lot of connection a lot of a node. **Logical Addressing** IP address appear here we have to have source address and destination address. Doing subnetting. **Routing** is finding the path from source to destination (shortest path). Address Transformation match the logical and physical using ARP protocol. **Multiplexing** if we have open multiple application it called package.

	Develop Software starting from this layers.
- **Transportation Layer** - Main is End-to-End message Delivery Control like open a browser have a lot of destination of IP address client can open a IP address to different IP address. Service-point (PORT) addressing map endpoint to another endpoint (map the process inside). Establish, maintain, terminate virtual circuit (design whether use TCP, UDP we define here)
- **Session Layer** - Layer that we can setup a session to communicated between process and process inside the application we called a session data is data communicated in  this layer. It need to make sure that synchronize the interaction between application need to create a software to handle it.
- **Presentation Layer** - Related to application how to represent the data. Translation. Format data. Data Structure. Encryption, compression and security.
- **Application Layer** - Application software

## Network Devices
- Repeater => normally not found but use (wireless extender or WiFi repeater) it will drop the speed by half is repeat we need to amplify the light amplitude if it long distant. Normally work on Layer 1.
- HUB (similarly to switch nowadays) => Send signal to 1 port and distributed to another. Divide into 2 part passive and active and its acts like repeater amplifying the signal to other devices. Working on layer 1.
- Switch => Device that running most of the connection LAN line nowadays running on Layer 1 and 2. Understanding MAC Address. Listen to one port looking the MAC address and forward to the exactly device. Its need a power to calculate what ports by view on the MAC table that memorize. If it don't it distributed to every port once its receive from that port it will memorize that port.
- Bridge => Running on Layer 3. Connect between network topology. One leg of the bridge is connect to the LAN line another connect to the wireless.
- Router => Layer 3. Router can understand layer 2 and 3 some can understand layer 4. Dealing with finding path routing. Access point is cheap than WiFi access point router.

## ITU
- IEEE802 Standards - Like Ethernet(802.3) or LAN line have there own name. Wireless (802.11), Starlink (802.16).

## When use byte or bit
1 Byte == 8 Bits. If we want to store to keep a data as a collector a size of a data called a bytes. When transmitted the data we send it serially not parallel as bits. Like when trying to install something 1GB we can calculate by 8 times of the internet.

## Bandwidth (Ideal)
Bandwidth is the amount of information that you can send during the time. (bps)
- Bandwidth is finite like maximum 1GB/s.
- Bandwidth is not free more u need the more u pay.
- Bandwidth is the key to design our network.
- Demand of bandwidth is ever increasing.
## Throughput (Real thing) 
is the measure of the amount of information.

### The factor that determine throughput.
- Internet devices(connect more get least)
- Type of data being transferred
- Network topology.
- Numbers of users.

## Transmission Media (Talk in physical layer)
- Copper Media (Copper line)
- Optical Media (Optics Fiber)
- Wireless Media

### Copper Media
	3 lines baseline(broadband) lanline 
- **Coaxial cable** use for TV and CCTV stop using this in data communication it a plastic black-white cover. Inside will be outer conductor and insulating material. Core is copper core. Bad thing because having 2 conductors speed and Through put 10Mb/s
- **Twisted-Pair Cable** using nowadays there are two type STP and UTP. Shielded and Unshielded. STP it will have thin metal film inside and separate twisted pair to protected electromagnetic interference and radio frequency interference. UTP is the same but no metal film. Color is solid orange and stripe orange, solid green and stripe green, solid blue and stripe blue, Black and grey. Throughput is 10 - 100 - 1000 - 2500 - 5000 and 10000 Mbps Max length is 100m otherwise will loss the amplitude of the signal. We need to twisted because of crosstalk if parallel i will generate the electromagnetic field and both of them will cause noise that we don't need. So if twisted the noise will canceled by themself not 100% but cancel.
- **Ethernet Cable Standard** TIA/EIA-568-AB method of for wiring and RJ45 Connector.
	nowadays having a switch to change between the straight and cross
	- Straight-through Cable Both have to have a same type end1 have A end2 must have A
	- Cross-through Cable have 1end A 1endB
	When connect computer to switch or router use straight through (higher layer level) if we need to connect from one computer to another computer we need cross over (same layer level).
	Cross-Over Cable using the red cable.
- Power Over Ethernet to provide the voltage over the LAN line on the pin 4 and 5 for negative pin 7 and 8 for the positive but the distance will be decrease to 40m.

### Optical Media
	One line only need 3 components.
- The light source.
- The transmission media.
- The detector: detect the light and dark generate the signal.
Consist of 3 parts: core glass, cladding glass and jacket (plastic).
Using the critical angle. Having 2 density of glass to force critical angle of the light reflection 1 cores can carry 1 TB/s.
#### Multimode and Single-mode.
Single-mode: small core super fast inside is very thin go longer than copper line because it light source no interfere source but its very easy to break it.
Multimode: thick core slower but can carry the light.
#### Connector standard 
LC, SC, FC. Green APC Blue UPC.
UPG - Ultra Physical Contact cutting cable straight get more loss than APC.
APC - Angled Physical Contact cutting angled get lower loss.
- LC support Single Mode both green and blue and Multi Mode on Blue. 500 mating cycles (put in put out times) and having lever lock-tab.
- FC (Fiber Optic Connector) metal scull in and out design for high vibration environment.
- SC Connector can push in and out 1000 mating cycles.

### Wireless Media
IEEE802.11
- 11g 2.4GHz using at home. 
- WiFi repeater or range extender 50% drop each repeater.
- Mesh need 2.4G + 5G, drop speed less than repeater.
- Mesh backhaul ethernet the best.