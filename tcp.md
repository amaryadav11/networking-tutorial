ip protocol can be used to send data from one computer to another across network, there is a limit how much data we can send in an ip packet the ip packet has to fit inside a data
link frame(PPP or Ethernet frame) in most of the cases PPP frame or ethernet frame carries 1500 bytes(MTU) of payload(ip packet). If we want to send data which is larger than
1500 bytes we need to split data into multiple packets there are couple of challenges in doint that
1. Packet loss (can be due to corruption in line(physical layer), frames interpreted wrongly, when router is updating routing table info) if we miss even one packet from our stream of 
   data then that data might not be useful so we need some mechanism to recover from these errors by retransmitting the missed or corrupted packet, also packet can arrive in different 
   order so we need to reorder it, different packets can take different routes to reach destination, there could be multiple convesatations going in between two computers
   multiple processes\apps in compA talking to different apps in compB, like tranferring two files between two computers how do we know which packet belongs to which file, if one comp
   is sending packets at a fast rate and other comp is not not able to process it at the same rate that also has to be handled, if a link is congested router will start droping packets
   so we need some sort of flow control so we can tell comp A to slow down if too many packets is dropped TCP solves all these problems it does this by providing byte stream service
   TCP features:
   1.connection oriented before sending any dat it eastablishes tcp connection(3 way handshake) its like phone call before anyone can tal you have to dial the number wait for the other
     person to answer and say hello then we can start the convesatation so there is connection setup process that takes first
   2. byte stream service- once the connection is eastablished either sides can start sending stream of bytes without having to think about how the split the data across different packets\
      how to create different packets in one end we can put stream of bytes in tcp and the same stream of bytes appear on other end tcp will group some bytes together and create a 
      segment(tcp header + data) that can fit into an ip packet
   3. reliable -  when tcp receives the segment on other end it send an acknowledgement back that way if an acknowledgement is not
      received within a timeinterval it can be retransmitted this way tcp provides reliability, it also keeps tacks the sequece of each segments it sends so it can reordered at the
      receiving end and remove duplicate packets that show up at the receiving end
      ![image](https://user-images.githubusercontent.com/23136463/113844817-8538d800-97b2-11eb-89ab-14621f06abf1.png)
      
      tcp packet is encapsulated\wrapped inside an ip packet and ip packet is encapsulated inside a frame(ethernet frame, PPP frame, Layer 2 frame)'
      ![image](https://user-images.githubusercontent.com/23136463/113845228-e8c30580-97b2-11eb-88e5-cbf381bac5ce.png)
      ![image](https://user-images.githubusercontent.com/23136463/113845340-07290100-97b3-11eb-973c-e19e3957c005.png)
      
      tcp port no is used to determin which packet belongs to which conversatation because there could be multiple conversatations(multiple tcp connections) going in between two computers
      each connection is identified by source ip add dest ip add source port and dest port the connection is bidirection so all the addresses will be flipped, checksum in tcp packet 
      is checksum of tcp header + tcp stream the sequence no is initialised to some no at beginning og connection for every byte that is sent sequence no is increased using this packets
      can be reordered and can be used to check if packet is duplicate in the acknowledgement field it will send the next sequence no it expects to receive
      
      ![image](https://user-images.githubusercontent.com/23136463/113846795-78b57f00-97b4-11eb-9d5f-59d3377ad1e2.png)
      
      the device that initiates the connection is called client and the other device to which its connecting is called server, client chooses a random client port to connect to sever on
      a particula port
      ![image](https://user-images.githubusercontent.com/23136463/113848481-24ab9a00-97b6-11eb-9e9d-e1cb94c3890a.png)
      ![image](https://user-images.githubusercontent.com/23136463/113848604-4ad13a00-97b6-11eb-9c6b-294dc7a8e656.png)





   
