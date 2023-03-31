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
auth_type PASS
auth_pass 1111
}
unicast_peer {
192.168.0.1
}
virtual_ipaddress {
192.168.0.50 dev enp0s3 label enp0s3:vip
}
}
```



### Node 2


![11](https://user-images.githubusercontent.com/126493876/229119906-02a8c39c-5d43-4dd5-a07d-42a1443d6696.png)

```rdt
vrrp_instance failover_test {
state BACKUP
interface enp0s3
virtual_router_id 10
priority 110
advert_int 4
authentication {
auth_type PASS
auth_pass 1111
}
unicast_peer {
192.168.0.2
}
virtual_ipaddress {
192.168.0.50 dev enp0s3 label enp0s3:vip
}
}
```


