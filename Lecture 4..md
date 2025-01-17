## Flow Control 
Keep the data safe both end.
It will have source and destination. 
![[Drawing 2024-12-25 13.15.42.excalidraw]]
### Stop and Wait
Easy way to send the data but not efficient if the data is big the data will be shading into a pieces. Example if have 10Tons if need to take it to another places. You need to go by one truck. Truck go back to receive and do it again.
![[Drawing 2024-12-25 13.18.27.excalidraw]]
So solving by Fragmentation MTU (Maximum Transfer Unit) 1500 Bytes.
But calculate give 1500 Bytes if u fragment too much u can't know where the error occurs.

## Flow and Error Control technique.
### Sliding Window Protocols
- A One-Bit Sliding Window Protocol.
- A Protocol Using Go Back: Sending the data and spotted an error it told to send the specific frame. Go back and send from that frame popular on Ethernet.
- A Protocol Using Selective Repeat: What every frame have an error it will told to resend that frame again. It need the buffer the whole side. It need more CPU time and memory for buffer.
### Sliding Windows Flow Control
![[Drawing 2024-12-25 13.46.09.excalidraw]]
**Stop and Wait - Diagram**
1 bits = $2^{1}=2$
$w=2^{0}=2^{1}-1=1$
![[Drawing 2024-12-25 14.04.16.excalidraw]]
**Go Back N-Diagram**
3 bits
$2^{3}=8 (0-7)$
$w=8-1=7$
![[Drawing 2024-12-25 14.12.07.excalidraw]]
#### Why Quota Win = $2^{k}-1$
- Eliminate the confusion go back or go forward next 0 or back 0.

**Selective Reject-Diagram** 
![[Pasted image 20241225143440.png]]
