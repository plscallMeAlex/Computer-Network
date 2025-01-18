# The Data Link Layer (2nd Layer)
Need a lot of security in this layer. "Node to node delivery" working on the MAC address. This layer the data that send from this layer called frame (framing). On layer 3 called packet. To make node to node smooth we do error control because error can happened every time. Flow control to get the maximum speed that have the same receiver and sender.
## Function of the data
Packet is on 3 layer.
Header Payload, ... is frame on 2 layer.

## Services Provided to Network Layer
(midterm)
- Virtual communication (like 2 layer here talk to another 2 layer).
- Actual communication (application go on 4,3,2,1 layer then 1 talk to another 1).

## Framing.
We have to construct a frame before send it out.

**A character stream without errors.**
| 5 1 2 3 4 | 5 6 7 8 9 | 8 0 1 2 3 4 5 6 |
 frame 1     frame 2     frame 3
 The beginning of the frame is identify that on that frame have many character

**With one error.**
| 5 1 2 3 4 | 7 6 7 7 8 9 8 0 |
error on 7 the frame will be 7 collector.

We have flag is the special collector at the end of the frame.
Flag -> Header -> Payload field(Package in 3 layer) -> Trailer -> Flag
![[Pasted image 20250118001922.png]]

### We use bit stuffing:
This method is safer after that will remove.
111111 -> flag (consecutive starting of the frame)
- 011101011101111111111110010 (111111 is starting flag mot allow 6 consecutive 1 inside)
- 0111010111**0**11111**0**11111**0**110010 (we stuff 0 bits make it totally difference)

## Error Detection & Correction.
- Error-Correcting technique it can detect and correct the error and the receiver if that error not much depend on how big of the frame.
- Error-Detecting technique (use in nowadays). It will check on the header if it error it will throw away and signal resend the data again.
The maximum that can send on the one frame (Maximum transfer unit).
### Error Detection 
Data ---> E = f(Data) ---v
     ---> Data[E]
 Called error detection coding.
 - Parity Bits will validate the number is even or odd. 1100_{0}, 1110_{1} but it detect the error happened 1 place.
 - CRC (Cyclic Redundancy Check) use for all communication use modulo 2 (XOR) so it gonna be this equation.
#### CRC Equation
T=(k+n) bit frame to be transmitted
M = k bits (Data or Payload data)
F =n bits (FCS Error Detection control)
P = pattern (a control function to generate FCS at n bits) = n +1 in binary.

$T=2^{n}M+F$
Ex: 
T 10 Base 
M = 20
P =3 
F = 20/3 = 6 + 2/3 ( 2 = FCS)
T =\[20]\[2]=202
	T = 20*10 - FCS = 200 +2 = 202

How to get F
dividing $2^{n}M/P$
$T=2^{n}M+R$ (R is FCS)
While R is the remainder.

**Ex1:**
Data - 10110010
P - 1001
need to shift $2^{n},n=3$
![[ex1]]
**Ex2:**
Data - 1001 1100
P - 1010
need to shift $2^{n},n=3$ bits
![[ex2]]