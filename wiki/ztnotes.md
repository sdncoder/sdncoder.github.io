#### Zero Trust
current problem:  
* number of FW  
* number of zones
* understand lateral movement 
* IAM complexity  
* lack of automation  
* peremiter based security has limitiations in the hybrid infrastrucutre environmnent (on-prem, cloud native, dispersed workers)  

what is future state:  
* 


solution:  
*  crawl - flatten zones and combine networks 
*  greenfield zero trust - what do new deployments need to do to be certified  
*  > what is recipie  - things you have to do with new deployment
*  path to zero trust  
*  what does final state look like  

#####  the network  
* one network and that network is the Internet  
* Zero Trust is needed to make that happen  
* all investments and work should be towards this goal  
#####  
* a solution that is solely reliant on the network is not zero trust  
*   zero trust assumes a hostile network
*     VPN tunnels for remote users; tunnels between the corporate enterprise and cloud services 
*     policy that relies on IP subnet based rules for access (location specific)  




ZTNA - build a tunnel from the corp network to the cloud.  user interface overlay on top of the tunnel to control what resources a user can access.  user tunnels to resource.  
*  ZTNA helps reduce visbility into application environments. 
*  relies on tunnels, that is a bottleneck.  
*  NETWORK RELIANT SOLUTION IS THE ANTITHESIS OF ZERO-TRUST.  ZT assumes the network is hostile
*
ZTAA - 
* performace and elasticity  
* cloud-native  
* when seeking an agentless VPN alternative  
* client and tunnel to office-less -- better experience  
* 

Avoid the Tunnel to "trust no one"  
- you dont need a tunnel for zero trust  
- ZTNA tunnel - secure the user in the network with more tunnels...wrong approach  
- 


