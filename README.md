# k3s demo
- master:   192.168.56.30
- worker1:  192.168.56.31
- worker2:  192.168.56.32


### 1. khởi tạo máy 3 máy ảo centOs7
vào từng thư mục master, worker1, worker2.
```shell
vagrant up
```

### 2. Cài đặt k8s cluster bằng k3s
1. master: 
```shell
curl -sfL https://get.k3s.io | K3S_KUBECONFIG_MODE=644 sh -
```

2. máy worker:
```shell
curl -sfL https://get.k3s.io | K3S_URL=https://192.168.56.30:6443 K3S_TOKEN=<token tại node master /var/lib/rancher/k3s/server/node-token> sh -

```