## to err is human; to propagate errors massively as scale requires automation

`code`

## topics
* [Automating the network deployment with Ansible](#automating-the-network-deployment-with-Ansible)
* [site reliability engineering the network backbone](#site-reliability-engineering-the-network-backbone)
* [containerlab modeling with cumulux vx](#containerlab-modeling-with-cumulus-vx)


## Automating the network deployment with Ansible
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

## constainerlab modeling with cumulux vx

macos

```
CLAB_WORKDIR=~/clab

docker run --rm -it --privileged \
    --network host \
    -v /var/run/docker.sock:/var/run/docker.sock \
    -v /run/netns:/run/netns \
    --pid="host" \
    -w $CLAB_WORKDIR \
    -v $CLAB_WORKDIR:$CLAB_WORKDIR \
    ghcr.io/srl-labs/clab bash
```
getting the Cumulux VX docker:
https://github.com/networkop/cx/

pull the latest vx docker:
`docker run -d --name cumulus --privileged networkop/cx:latest`




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

https://mermaid-js.github.io/mermaid/#/
