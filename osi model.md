![image](https://user-images.githubusercontent.com/23136463/113200520-06114480-9286-11eb-80a6-01332bf7f913.png)
![image](https://user-images.githubusercontent.com/23136463/113200820-6ef8bc80-9286-11eb-9c13-e8f7685ac0a6.png)
![image](https://user-images.githubusercontent.com/23136463/113201002-a5ced280-9286-11eb-876c-c33d43d89aee.png)
If comp A want to send an ethernet frame to comp B it will create an ethernet frame with destination address as comp B ethernet address since no one has that mac address
on etherner network on LHS it will be ignored by all and the etherner frame will not be able to go beyond the LHS etherner n/w marked in red
SFO can forward the ethernet frame over PPP link to DEN that will not work because PPP frame does not uses destination mac address so it is not possible because DEN will not have 
any idea what to do with that frame so we need other type of address that is not specific to ethernet protocol or PPP protocol that can be used across different n/ws
if comp B has some sort of universal address that is understood everywhere then all the devices in middle can use that address to forward the data to correct destination
so the address used is called ip address Interner means between different n/ws 

now when the ethernet frames arrives at SFO router it opens the ethernetframe and retrives the destination ip address from ip packet and decide  whether the packet should be
forwarded to iterface 2 or interface 3 it checks the nework address and routing table and based on that it forwards the packet to correct interface if it decides to forward ip 
packet to interface 3 it create a new ppp frame and add the ip packet to it and send it to the next router DEN then DEN router does the same thing
router reeives packet on one interface and forward it to other interface each router has routing\forwading table
router selects the longest match
![image](https://user-images.githubusercontent.com/23136463/113203572-d49a7800-9289-11eb-8e42-1b42c4141cc7.png)
If a comp A wants to send some data to a comp on different n/w it forms the ethernet frame and sets the destination ethernet address as router ethernet address and destination ip address
as other comp ip address how comp A knows that it has to forward the ethernet frame to router

comp A knows that anything connected to ethernet will have prefix 192.168.9/24 so if it wants to send anything to 192.168.9 it will be in same n/w if it has to be send somewhere else
for anything else it will send it to gateway(router) it has the router ip but in order to send the ethernet frame to router it has to get the router mac address so comp a will
send a broadcast message on n/w who has this ip address(router ip) router will reply with its mac address(arp protocol is used for this)
![image](https://user-images.githubusercontent.com/23136463/113205807-5095bf80-928c-11eb-8d2f-1b59adc1b4ed.png)
Now comp a has router ethernet address now it can forward the packet to router
