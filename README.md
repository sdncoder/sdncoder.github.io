## network stuff

`code`

## topics
* [Automating the network deployment with Ansible](#automating-the-network-deployment-with-Ansible)
* [Go](#go)
* [containerlab modeling with cumulux vx](#containerlab-modeling-with-cumulus-vx)


## Automating the network deployment with Ansible
standardization and automation
verify base config across network
CICD for the network infrastrucutre has limitations
The "test" ability is limited.   Example. using BatFish, GNS, or VIRL is limited.
These are not real network tests.
CICD in the web space..the build truly is the same; just using a differenet DNS name bewteewn stage/dev/prod.
Testing your network config againt BatFish equates to is this config standardized (ACL, etc); there are better ways to really do that ~ lab router


## Go
install snap package manager
`sudo apt install snapd`

install go
`sudo snap install go --classic`




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


for macos:
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


#### other stuff


https://www.packetcoders.io/introduction-to-scrapli/
Scrapli supports the parsing libraries Genie, TTP and TextFSM. 
https://dteslya.engineer/network_automaiton_101/#scrapli

#### Docker host NAT
https://blog.oddbit.com/post/2014-08-11-four-ways-to-connect-a-docker/

#### zettel
```
init.vim
  1 set number
  2 syntax on
  3 set textwidth=80
  4 set ignorecase
```

```
  1 echo 'zettel'
  2 let g:zettelkasten ="/home/netadmin/notes/"
  3 command! -nargs=1 NewZettel :execute ":e" zettelkasten . strftime("%m-%d-%Y"    ) . "-<args>.txt"
  4 nnoremap <leader>nz :NewZettel
```


