## infrastructure as code


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

