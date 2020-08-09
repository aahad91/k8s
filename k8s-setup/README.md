# Step to perform after vagrant up is completed

- ssh into node-1

```bash
vagrant ssh node-1

sudo vim /etc/default/kubelet

# add the following into file 
KUBELET_EXTRA_ARGS=--node-ip=192.168.50.11
:wq

sudo systemctl daemon-reload
sudo systemctl restart kubelet
```

- ssh into node-2

```bash
vagrant ssh node-2

sudo vim /etc/default/kubelet

# add the following into file 
KUBELET_EXTRA_ARGS=--node-ip=192.168.50.12
:wq

sudo systemctl daemon-reload
sudo systemctl restart kubelet
```

