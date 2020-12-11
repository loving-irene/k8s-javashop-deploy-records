#### 构建API镜像

需要安装 `maven` 以及 `jdk1.8`。

在build和push动作之前，需要先使用命令行登录下 docker，记录下授权状态，然后才能push上去。

登录命名行命令在阿里云对应镜像的基本信息中查看，这里使用的密码是登录密码，不是访问凭证。

#### 配置docker私服秘钥

这里的秘钥主要是 k8s 在自动拉取对应的镜像时使用，配置时注意密码是访问凭证，不是登录密码。

因为前面在构建 API 镜像时已经使用`docker login`进行了授权，这里配置私服秘钥时，直接将之前生成的文件导入到k8s中即可。

只需要改动对应位置即可。
```
kubectl create secret generic your_secret_name \
     --from-file=.dockerconfigjson=<path/to/.docker/config.json> \
     --type=kubernetes.io/dockerconfigjson
     --namespace=ns-javashop
```

#### 部署配置中心

源码库中的 config 下的文件可能存在格式问题，在排错的过程中需要注意一下。

#### 部署API

验证可以使用集群中的任意机器IP，不过要等所有的服务都起来才可以。