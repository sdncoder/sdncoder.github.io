### Apline Linux FRR  
use Alpine with FRR for VM based router  
download extended image, run in RAM and recommended for router use  

setup:  
Alpine network config is not set by default, DHCP setup of image:  
`vi /etc/network/interfaces`  

```
auto eth0  
iface eth0 inet dhcp
```

