### Задание 1

![10](https://user-images.githubusercontent.com/126493876/229119205-4cff470a-92d9-4915-915d-1b89e782c8d8.png)

```rd
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



