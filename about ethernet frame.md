How computer knows that a particular group of 8 bits makeup a byte from a bunch of stream of 0's and 1's, 
how receiver knows the first byte start here second bytes start here and so on

Bytes are put\wrapped\grouped into frames which can be 1000 bytes long if we know where a frame
begins then we can find the correct location of 1st,2nd and ... bytes boundaries

Types of framing used
1. HDLC High Level Datalink Control -> commonly used in ISP networks and other large networks
   it uses a special bit pattern called flag 01111110 if the receiver sees the flag it knows 
   the very next bit is the starting of frame(the 1st byte of the frame)
   
   what if data that we are send has the pattern same as flag when using HDLC it follws another rule
   if data contains the flag it stuffs one zero after five 1's to prevent this problem
   ![image](https://user-images.githubusercontent.com/23136463/113194489-d448af80-927e-11eb-85d9-e3032181424b.png)
   
  2. Ethernet frame
    In ethernetframe there is inter frame gap period of silence the voltage in wire is zero 
    ![image](https://user-images.githubusercontent.com/23136463/113194967-5a64f600-927f-11eb-817a-86d4070814b0.png)
    ![image](https://user-images.githubusercontent.com/23136463/113195049-7072b680-927f-11eb-9ae0-4a03adea1550.png)
    In theory we can send one byte in an ethernet frame but it will not be efficient we can send more and more no
    of bytes in an ethernet frame but in case of an error the ethernet frame has to be resend so there is a tradeoff
    between efficiency and being able to quick recover from any error by sending small frames in practise frame size
    varies from 64 bytes to 1500 bytes in high performance network in can be 9000 bytes long called jumbo frames
    # Point to Point link
    one computer directly computer to another computer via cable(point to point data link)
    if one computer wants to send information it puts that data into frames and other computer decodes it
    point to point links is commonly used in larger network like ISP networks point to poin links are used to connect networking equipments like two routers etc 
    mainly uses fiber optics cables for long distances
    # Multipoint link or Broadcast link(cable modem home internet connection same cable is shared with multiple users, multiple computers connected together via ethernet switch)
    ![image](https://user-images.githubusercontent.com/23136463/113197130-ed069480-9281-11eb-8d8f-4c955bd1d8b0.png)
    # Format of ethernet frames
    Ethernet frame has sorce and destination address because more than one computer is connected to same ethernet network each computer has a unique ethernet address (mac address)
    if one computer wants to send data to all it puts the broadcast address all f's in destination address ethernet type tells the format or type of payload that helps the receiver to decode the payload in most cases the payload will be ip packet(0800) the payload size is between 64-1500 bytes long in high performance n/w it can be as large as 9000 bytes the sender will compute the checksequence(src,dest add, ether type and payload) of all the data in the frame and will add to frame check sequence the receiver will use it to verify the data is not corrupted in transit if its corrupted receiver will ignore it and sender has to resend it
    ![image](https://user-images.githubusercontent.com/23136463/113199134-656e5500-9284-11eb-9051-98a04df50b4e.png)
    
    
    
 # Point to Point protocol is used in point to point data link
 
 PPP frame format- it uses hdlc framing technique
 ![image](https://user-images.githubusercontent.com/23136463/113199752-1ecd2a80-9285-11eb-83e3-e7e372b2ba4b.png)

    


