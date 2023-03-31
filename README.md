### Задание 1

![7](https://user-images.githubusercontent.com/126493876/229067275-5af67e2d-078d-4ee4-bc97-2cf3f3c02d3e.png)

![8](https://user-images.githubusercontent.com/126493876/229067345-7f24c76a-6908-4ec6-90ff-9b2c7adfc50e.png)

vrrp_instance failover_test {

state MASTER

interface enp0s8

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
192.168.0.50 dev enp0s8 label enp0s3:vip
}
}

### Node 2

![4](https://user-images.githubusercontent.com/126493876/228545690-7369da66-9d52-4163-9b4e-44f1e54a6fac.png)

![5](https://user-images.githubusercontent.com/126493876/228545757-582bc74b-b27e-4eef-8518-48385f86c7d9.png)

![6](https://user-images.githubusercontent.com/126493876/228545799-4a70090c-25b8-47c8-8971-a743715e7eb1.png)
