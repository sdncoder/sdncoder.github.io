## on building an automation framework for network engineering teams  

_network teams need to understand Ansible and Terraform use cases and the fundamentls of configuring network devices using them:_   
1. they work and allow teams to speed up deployments with consistency of the configuration  
2. allows the integration of the network "piece" of the deployment to be integrated in the larger infrastructure as code build  
3. if network engineers don't learn these tools they will get their lunch eaten by DevOps  




Mermaid diagramming  
`https://mermaid-js.github.io/mermaid/#/`  

state diagram  
```
   stateDiagram
    direction LR  # set direction
    [*] --> main
    main --> branch
    branch --> review
    review --> merge
    merge --> main
```
```mermaid
   stateDiagram
   direction LR
    [*] --> main
    main --> branch
    branch --> review
    review --> merge
    merge --> main
 ```
 
 ```
  state branch {
    direction LR
    change --> review 
    review --> merge
    }
 ```
 ```mermaid
   stateDiagram
   direction LR
    [*] --> main
    main --> branch
    state branch {
    direction LR
    change --> review 
    review --> merge
    }
    merge --> main
 ```

