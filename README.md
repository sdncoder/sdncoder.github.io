## to err is human; to propagate errors massively as scale requires automation

`code`

## topics
* [Automating the network deployment with Ansible](#automating-the-network-deployment-with-Ansible)
* [Pre-deployment configuration validation with BatFish](#pre-deployment-configuration-validation-with-BatFish)
* [containerlab modeling with cumulux vx](#containerlab-modeling-with-cumulus-vx)


## Automating the network deployment with Ansible
standardization and automation
verify base config across network
CICD for the network infrastrucutre has limitations
The "test" ability is limited.   Example. using BatFish, GNS, or VIRL is limited.
These are not real network tests.
CICD in the web space..the build truly is the same; just using a differenet DNS name bewteewn stage/dev/prod.
Testing your network config againt BatFish equates to is this config standardized (ACL, etc); there are better ways to really do that ~ lab router


## Pre-deployment configuration validation with BatFish
#### Cumulus VX
https://gitlab.com/permitanyany/cldemo2

https://batfish.readthedocs.io/en/latest/formats.html#cisco

start container in docker:
`docker run -p 8888:8888 batfish/allinone`

3 files are used concantenated into a single file.
```
/etc/network/interfaces
/etc/cumulus/ports.conf
/etc/frr/frr.conf
```
each device file goes into configs folder

template:
```
(
  # hostname
  echo $hostname

  # Signal start of /etc/network/interfaces
  echo "# This file describes the network interfaces"
  cat /etc/network/interfaces
  echo 

  # Signal start of /etc/cumulus/ports.conf
  echo "# ports.conf --"
  cat /etc/cumulus/ports.conf
  echo 

  # Signal start of /etc/frr/frr.conf
  echo "frr version"
  cat /etc/frr/frr.conf
  echo
)
```



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
