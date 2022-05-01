### SR MPLS notes  

MPLS "classic":  
* MPLS "classic" (LDP and RSVP-TE) control-plane was too complex and lacked scalability.   
* LDP is redundant to the IGP.  
* MPLS TE objective was to create circuits with hop-by-hop signaled state.  
* RSVP-PE is not ECMP-friendly.  ECMP is fundamental to IP.  
* RSVP-TE is "always on" to account for BW and a full-mesh of PE-to-PE tunnels is required.  
* N^2 x K tunnels  N=nodes K=tunnels  
* result is operational complexity with limited scale.  
