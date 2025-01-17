# DHCP
Dynamic Host Configuration Protocol is auto assign the IP to the machine.
![[Pasted image 20250108133325.png]]
It need to return the IP back if it reach the time limit and rent it again if i want to use. So it can be difference IP.

Can be attack by MITM (Man In The Middle Attack) it act as the DHCP server and copy the traffic before forwarding it to the real router.

Prevent by DHCP spoofing and DHCP snooping.

# Media Access Control Sub-layer
Data link layer have 2 two sub layers inside.
MAC control access media to send the data it will have logical link control on top for frame format wireless. 

## The Channel Allocation
- Static Channel - For me and only me no one can access this.
- Dynamic Channel - Share with other to use media as well.

### Dynamic 
Channel
Separate into multiple station any device called station. One single channel share with many channel problem can be happened. 

**Continuous Time** - Send data cand send anytime.
**Slotted Time** - The time divided into slotted have to wait the beginning next time slot to send the data.

**Carrier Sense** - Send to check someone using that channel need to wait to prevent the data loss (normally communication).
**No Carrier Sense** - Don't care just send it (use in some protocol ALOHA).

#### Pure ALOHA
In pure ALOHA, is satellite protocol communication use no carrier sense because it far from the satellite so it no need to wait the channel.
![[Pasted image 20250108140430.png]]
But it have a lot of problem if the data collide.
![[Pasted image 20250108140625.png]]
IEEE 802.3 (CSMA/CD) Ethernet LAN line.
It better throughput than non carrier sense.

Ethernet LAN line using the Manchester encoding.

## Encoding
1. **Binary Encoding** have a problem with electric shock during the dry temperature like want to send consecutive 1 for long time it charge the copper line with electric for long time to prevent it ether avoid long 1 by represent it 1 by 10, 0 by 01 called Manchester encoding.
2. **Manchester Encoding** make representing the 1 to 10 and 0 to 01 #MightOnExam.
3. **Differential Manchester Encoding** using the sensor to detect the state change is 0 no change is 1 make the machine faster.

## Frame formats
![[Pasted image 20250108144824.png]]
The first 8 bytes to measure the delta T.
The next 48 bytes contain the MAC address of the destination it put in the front because in the past using the hub find the machine.

If Data is 0 bytes Pad is 46,

| Data | Pad |
| ---- | --- |
| 0    | 46  |
| 1    | 45  |
| ...  | ... |
| 46   | 0   |

It tell the Min Frame Size:
P(8) + MAC-D(6) + MAC-S(6) + Lg(2) + 46 + CRC(4) minimum.

Check-sum (CRC) is check the above.

### Collision Detection
![[Drawing 2025-01-08 15.07.11.excalidraw]]
detect collision tell the A this data is no fully sent.

## The Binary Exponential Backoff
If the station sending a data detect collusion that station need to send it again. It done by time slot $2^{n}$ where n is the number of collusion.
![[Drawing 2025-01-08 15.14.11.excalidraw]]
Use this to avoid by random slot but can use small software to specific slot.

## LAN Topology
- Ethernet 802.3
- Token Ring 802.4
- Token Bus 802.5
