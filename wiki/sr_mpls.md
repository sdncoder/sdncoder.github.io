### SR MPLS notes  

MPLS classic:  
* MPLS "classic" (LDP and RSVP-TE) control-plane was too complex and lacked scalability.   
* LDP is redundant to the IGP.  
* MPLS TE objective was to create circuits with hop-by-hop signaled state.  
* RSVP-PE is not ECMP-friendly.  ECMP is fundamental to IP.  
* RSVP-TE is "always on" to account for BW and a full-mesh of PE-to-PE tunnels is required.  
* N^2 x K tunnels  N=nodes K=tunnels  
* result is operational complexity with limited scale.  

IPFRR:  
* shorter the explicit path the better.  
* don't steer the packet around the failure and back at the other end.  
* reroute around the failure and release as soon as possible to a natural IP path.  
* microloop avoidance - prevent packet drop due to inconsisten transient state between converging routers.  

Segment Routing:  
* distribute labels in the routing protocol
* centralized optimization with traffic-engineering based on prefix segments

OpenFlow approach
* Centralize controller takes too much time to send updates and install in per router HW.  

Hybrid centralized/distributed network approach
* network would maintain a level of distributed intelligence (IS-IS distribution of prefix and node segments).  
* controller or head-end PE would build paths based on a list of segments.
* combine distributed intelligence at the nodes (shortest-path, FRR, microloop avoidance) with head-path segment lists or PCE.  

TI-LFA:  
* point of local repair pre-computes the post-convergence path to a destination.  
* backup path is installed per destination prefix.  

with SR you avoid parameters, options and tuning  == TI-LFA, microloop avoidance.
good network design is based on a broad overview of complexity, good knowledge of the cost of that complexity, and wise choices of the trade-offs.

### Segment Routing  
* source routing paradigm.  
* head-end node chooses path and steers a packet by inserting an ordered list of segments in the packet header.  
* nodes on path do not maintain state information.  
* a segment is an instruction.  
*   


