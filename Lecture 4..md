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
#### **Process:**

|Step|Sender's Action|Receiver's Action|Notes|
|---|---|---|---|
|1|Sends F0F0F0|Receives F0F0F0|Receiver processes F0F0F0.|
|2|Waits for ACK0ACK0ACK0|Sends ACK0ACK0ACK0|Sender receives ACK0ACK0ACK0.|
|3|Sends F1F1F1|Receives F1F1F1|Receiver processes F1F1F1.|
|4|Waits for ACK1ACK1ACK1|Sends ACK1ACK1ACK1|Sender receives ACK1ACK1ACK1.|
1 bits = $2^{1}=2$
$w=2^{0}=2^{1}-1=1$
![[Drawing 2024-12-25 14.04.16.excalidraw]]
**Go Back N-Diagram**
#### **Process:**

|Step|Sender's Action|Receiver's Action|Notes|
|---|---|---|---|
|1|Sends F0,F1,F2F0, F1, F2F0,F1,F2|Receives F0,F1,F2F0, F1, F2F0,F1,F2; ACK2|Receiver acknowledges F0,F1,F2F0, F1, F2F0,F1,F2.|
|2|Sends F3,F4,F5F3, F4, F5F3,F4,F5|F4F4F4 is corrupted; ACK3|Receiver discards F4,F5F4, F5F4,F5.|
|3|Retransmits F3,F4,F5F3, F4, F5F3,F4,F5|Receives F3,F4,F5F3, F4, F5F3,F4,F5; ACK5|Receiver acknowledges up to F5F5F5.|
3 bits
$2^{3}=8 (0-7)$
$w=8-1=7$
![[Drawing 2024-12-25 14.12.07.excalidraw]]
**Comparison Between Stop & Wait and Go-Back-N**

| Feature               | **Stop & Wait**                 | **Go-Back-N**                                              |
| --------------------- | ------------------------------- | ---------------------------------------------------------- |
| **Frames in Transit** | 1 at a time                     | WWW (window size) frames                                   |
| **Error Handling**    | Retransmits the single frame    | Retransmits the erroneous frame and all subsequent frames. |
| **Efficiency**        | Low (waiting for ACK per frame) | High (better channel utilization).                         |
| **Use Case**          | Simple, low-latency connections | High-latency, high-throughput communication                |
**Summary:**
- **Stop & Wait:** Simple but less efficient due to idle time.
- **Go-Back-N:** Improves efficiency by sending multiple frames, but retransmits more frames when errors occur.
#### Why Quota Win = $2^{k}-1$
- Eliminate the confusion go back or go forward next 0 or back 0.

**Selective Reject-Diagram** 
![[Pasted image 20241225143440.png]]
