**On Network Automation**  
 _a practial approach towards a network engineering CI/CD pipeline, scripting, and parsing_          

**Tenets:**    
* A CI/CD pipeline should be the only way to deploy network equipment to production.  
* The CD of the pipeline in large-scale networks has limiations and risk that should be accounted for with a modified workflow.  
* Vendor and commercial network tools lead to "death by subscription", open-source and scripting should be used to mitigate that.  

The **Network CI (integration)** uses the version control build of main-->branch-->review-->merge.  
* Continuous Integration - automate the integration of configuration changes.  

The **Network CD (delviery and deployment)**   
* Continuous Delivery - automate the test.    
* Continuous Deployment - automate production deployment.    

**_Continuous Delivery has limiations in network engineering as a "test" production network is non-existent._**    
**_Continuous Deployment has risk as their is no manual gate at a stage before push to the production network._**    

**The Repostiories:**
 
* Ansible playbooks:  [playbooks](https://github.com/sdncoder/playbooks)  
* Python examples:   [python](https://github.com/sdncoder/pyScripts)  
* Robot Framework:  [robot scripts](https://github.com/sdncoder/robot)    
* AWK, SED, Perl, TextFSM:  [text parsing](https://github.com/sdncoder/text-parsing)      
* NetworkX modeling:  [MPLS SR](https://github.com/sdncoder/sr-te-networkx)  
* Containerlab simulation:  [Containerlab](https://github.com/sdncoder/models) 
* Diagams as code:  [mermaid](https://github.com/sdncoder/diagrams)      
