#### 提前准备

需要提前安装一些工具

```
yum install -y vim git
```


#### 开始部署
执行`ansible-playbook site.yaml`命令之后，得到如下的结果图则正常。如果有 fail，可以尝试再执行部署命令一次。最终的结果如何，可查找下面的各节点图。

如果启动的容器数量对不上，可先忽略，只要部署ok，最后可以通过操作管理台来恢复正常。如果管理台有 fail，可以通过删除重启的方式处理。

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