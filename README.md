## on building an automation framework for network engineering teams  

_network teams need to understand Ansible and Terraform use cases and the fundamentls of configuring network devices using them:_   
1. allows teams to speed up deployments with consistency of the configuration  
2. allows the integration of the network "piece" of the infrastructure as code  






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

