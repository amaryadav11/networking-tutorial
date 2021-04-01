![image](https://user-images.githubusercontent.com/23136463/113331847-0ec55180-933e-11eb-97a1-376d0b1a574f.png)
![image](https://user-images.githubusercontent.com/23136463/113331920-256ba880-933e-11eb-9f04-78fc539685e4.png)
![image](https://user-images.githubusercontent.com/23136463/113332057-51872980-933e-11eb-938a-caacdd8736bd.png)
ip packet can be send inside PPP or ethernet frame r any layer 2 framing protocol, inside ip packer protocol field tells the type og payload ip packet carries(tcp or udp),
in enternet frame ethertype tells the type of payload it carries basically one protocol encapsulates another protocol each protocol has fixed responsibility(single resposilbility principle)
ip packet has a options field whose length can vary so it has a field called IHL(Ip Header Length) that is used to know from where data\payload starts normally IHL is 5 (five 32 bit rows)
type of service field is used to decide the priority of traffic it is used in routing protocol when router communicates with each other to exchange routing information since
routing info is of high priority so router may want to prioritize that traffic total length identification flags fragmentoffset is used in ip fragmentation, TTl is a 8 bit no that is
set the sender of the data and each router that the data goes through decrement the value by one and if become one the router will discard the packet it is done to prevent loops
loops can be created in a n/w but it happens for a short duration generatty happens when routing info is being updated etc we do a checksum check at data link layer at ip layer also
we have a checksum for ip header(its kind of redundant)
![image](https://user-images.githubusercontent.com/23136463/113334172-028ec380-9341-11eb-939b-d091b7f34593.png)
Router used the destination address to deliver the packet to correct destination

Router extracts the n/w address(n/w prefix) from all the routes in routing table and matches it with destination ip address like id route is 192.168.20.0/24 then it will extract 1st
24 bits from route and matches it with 1st 24 bit of ip address if it matches it send to that interface (longest match is selected)
![image](https://user-images.githubusercontent.com/23136463/113334799-c019b680-9341-11eb-9309-16b3fd7f71a6.png)
![image](https://user-images.githubusercontent.com/23136463/113335255-4f26ce80-9342-11eb-92ff-188c0154c5d0.png)
![image](https://user-images.githubusercontent.com/23136463/113335334-6960ac80-9342-11eb-9fa3-1e011a72f68a.png)
if there is no to (ip address) it means that particular interface is directly connected to that network so now it makes a arp request to get the destination comp ethernet address 
then create an ethernet frame and send that ip packet to destination comp, now destination computer will get the source address and do the same thing in case of nat private ip
is replaced with public ip

metric tells the distance if metric is 3 destination comp is 3 hop away including current router
two paths to reach to a n/w
![image](https://user-images.githubusercontent.com/23136463/113336854-99a94a80-9344-11eb-9f35-8f7d1cf51382.png)
