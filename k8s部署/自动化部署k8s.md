#### 开始部署
执行`ansible-playbook site.yaml`命令之后

![部署完成图](https://i.ibb.co/L6ywvh7/k8s.png)

##### master节点

`ansible`部署完成之后`master`节点上的镜像和容器服务。
![master节点](https://i.ibb.co/TTYqxdY/master.png)

##### node节点

`ansible`部署完成之后`node`节点上的镜像和容器服务。
![node节点](https://i.ibb.co/rMxn7bN/node.png)


`kubectl create -f /opt/kubernetes/role.yaml`如果报错

![role](https://i.ibb.co/M6RGM7F/role.png)

可以忽略不管，在部署阶段已经完成了这个动作，继续下一步即可。