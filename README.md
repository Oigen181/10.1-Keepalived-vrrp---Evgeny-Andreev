### Задание 1

![7](https://user-images.githubusercontent.com/126493876/229067275-5af67e2d-078d-4ee4-bc97-2cf3f3c02d3e.png)

![8](https://user-images.githubusercontent.com/126493876/229067345-7f24c76a-6908-4ec6-90ff-9b2c7adfc50e.png)

vrrp_instance failover_test {

state MASTER

interface enp0s3

virtual_router_id 10

priority 110

advert_int 4

authentication {

auth_type AH

auth_pass 1111

}

unicast_peer {

192.168.0.1

}

virtual_ipaddress {

192.168.0.50 dev enp0s3 label enp0s3:vip

}

}

### Node 2


![7](https://user-images.githubusercontent.com/126493876/229068371-1f516f1c-1939-4e0c-9021-0edefaa64d6e.png)

vrrp_instance failover_test {

state BACKUP

interface enp0s3

virtual_router_id 10

priority 110

advert_int 4

authentication {

auth_type AH

auth_pass 1111

}

unicast_peer {

192.168.0.2

}

virtual_ipaddress {

192.168.0.50 dev enp0s3 label enp0s3:vip

}

}



