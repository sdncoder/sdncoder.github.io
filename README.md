## re-thinking building and managing large scale production network infrastructure

`code`

## topics
* [a network engineering pipeline](#a-network-engineering-pipeline)
* [site reliability engineering the network backbone](#site-reliability-engineering-the-network-backbone)
* [capacity planning mpls segment routed networks using R programming](#capacity-planning-mpls-segment-routed-networks-using-R-programming)


## a network engineering pipeline
standardization and automation
verify base config across network
CICD for the network infrastrucutre has limitations
The "test" ability is limited.   Example. using BatFish, GNS, or VIRL is limited.
These are not real network tests.
CICD in the web space..the build truly is the same; just using a differenet DNS name bewteewn stage/dev/prod.
Testing your network config againt BatFish equates to is this config standardized (ACL, etc); there are better ways to really do that ~ lab router


## site reliability engineering the network backbone
use software and automation to solve network problems

if config is not standard, if new routers are not added to monitoring systems, if the information about the network is not accurate; reliablity will decrease...it will be a "network problem". 

## capacity planning mpls segment routed networks using R programming

```mermaid
graph TD;
    A-->B;
    A-->C;
    B-->D;
    C-->D;
```

```mermaid
gitGraph:
options
{
    "nodeSpacing": 150,
    "nodeRadius": 10
}
end
commit
branch newbranch
checkout newbranch
commit
commit
checkout master
commit
commit
merge newbranch
```

