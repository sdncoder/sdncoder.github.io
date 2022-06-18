### Apline Linux FRR  

setup:  
Alpine network config is not set by default, DHCP setup of image:  
`vi /etc/network/interfaces`  

```
auto eth0  
iface eth0 inet dhcp
```

