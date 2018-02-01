Rancher Playground
---

> Playing around with Rancher.  OSX with VirtualBox and Vagrant

Steps:

- Change in `Vagrantfile` the `forwarded_port` for the service port you need
- VirtualBox
- `$ vagrant up`
- Rancher server running on Host machine
  * `$ docker run -d --restart=unless-stopped -p 8080:8080 rancher/server:latest`
- Get the gateway of the VM `[root@vm]# netstat -rn`
- In the Rancher server, go to http://localhost:8080/admin/settings and change the Host Registration URL to http://GATEWAY:8080
- In Rancher server running on host, add a host, and add `10.0.0.123` in the `Host public IP`
- run command in the VM given by the rancher server: (replace localhost with the gateway found in `netstat -rn`)
