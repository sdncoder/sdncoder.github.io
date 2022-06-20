### IPFM - IP fabric for media  

* L3 Spine and leaf CLOS architecture has proven to be flexible and scalable.  
* No matter where the receiver is connected, the path always involves a single hop through the spine; providing deterministic latency.
* L2 network can be simple to build and need less planning for scale; it has a very large failure domain.  
* In a L2 network, traffic is always flodded to the multicast router or querier.  
* L3 multicast networks contain the fault domain and forward traffic only when there are active receivers.  


#### Standards  
SMPTE 2110 - video, audio, ancillary data over IP.  
AES 67 (Audio Engineering Society) - audio over IP.    


#### L3 protocols  
*  PIM - enables routing multicast between networks  
*  IGMP - protocol where the receiver (destination) signals the intent to join a source or leave a source  

Broadcast controller - communicates directly with the IP endpoint or gateway to 'trigger' IGMP join and leave the network.   Network delivers new flow to the destination.  *this is destination timed switching*  

#### Non-Blocking Multicast  (Bandwidth Aware PIM)  
* When multiple paths exist between source and destination in an IP network.  For every request for a new flow, PIM choses one of the available paths for the flow path using a hash.  
* Hash does not consider BW.  No guarentee of equal distribution of BW across links.  
* PIM sets up flow path.  
* PIM is very efficient but lacks the ability to use BW when setting up a flow path.  
* Cisco NBM on NX-OS to make PIM intelligent.  
* NBM brings BW awareness to PIM.  
* NBM and PIM work together to prevent oversubscription.  

#### NBN modes  
*  Goal of NBN is to ensure that flows are load balanced and that all paths are utilized; and prevent oversubscription.  
*  NBM Active mode - Nexus switches are responsible for BW management.  
*  NBN Passive mode - use SDN.  

#### Desiging a non-blocking spine and leaf CLOS fabric  
In an ideal senario the sender leaf (first hop router) sends one copy of the flow to one spine switch. The spine creates N copies, one for each receiver leaf switch with requesting receivers for that flow.   The reciver leaf (last-hop router) creates on N copy per local receiver connected on the leaf.  
* To ensure CLOS network remains non-blocking, a sender must have enough bandwidth to replicate all of its local senders to all spines.  
* BW of all senders on a leaf must equal BW of the links going to each spine from that leaf.  
* In broadcast most endpoints are unidirectional - placement of senders and receivers are important to ensure CLOS architecture is non-blocking.  




#### Relevant links:  
https://www.cisco.com/c/en/us/products/collateral/switches/nexus-9000-series-switches/white-paper-c11-738605.html
