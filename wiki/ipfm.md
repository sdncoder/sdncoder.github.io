### IPFM - IP fabric for media  

Spine and leaf CLOS architecture has proven to be flexible and scalable.  
No matter where the receiver is connected, the path always involves a single hop through the spine; providing deterministic latency.
L2 network can be simple to build and need less planning for scale; it has a very large failure domain.  
In a L2 netwokr, traffic is always flodded to the multicast router or querier.  L2 multicast networks contain the fault domain and forward traffic only when there are active receivers.  

#### Standards  
SMPTE 2110 - video, audio, ancillary data over IP.  
AES 67 (Audio Engineering Society) - audio over IP.    

#### L3 protocols  
*  PIM - enables routing multicast between networks  
*  IGMP - protocol where the receiver (destination) signals the intent to join a source or leave a source  

Broadcast controller - communicates directly with the IP endpoint or gateway to 'trigger' IGMP join and leave the network.   Network delivers new flow to the destination.  *this is destination timed switching*  





https://www.cisco.com/c/en/us/products/collateral/switches/nexus-9000-series-switches/white-paper-c11-738605.html
