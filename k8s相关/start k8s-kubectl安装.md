## Start K8s 1
### 容器云操作指南（1）
### <一> 创建集群（k8s）
使用后台操作即可。
### <二> 创建命名空间（namespace）
使用后台操作即可。
### <三> 镜像仓库
创建镜像仓库：首次进入镜像仓库，按提示操作即可。
Mac电脑本地登录私有镜像仓库
登录镜像仓库：
```
sudo docker login --username=[username] hub.baidubce.com
```
如果登录失败可使用如下指令后再次登录：
```
sudo su root
```
本地build docker image：
```
docker build -t hub.baidubce.com/[namespace]/[server-name]:1.0.1 .
```
push image 到私有镜像仓库：
```
docker push hub.baidubce.com/[namespace]/[server-name]:1.0.1
```
在控制台即可查看到此镜像。

### <四> kubectl管路集群
Mac安装kubectl
```
curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.12.4/bin/darwin/amd64/kubectl
chmod +x ./kubectl
sudo mv ./kubectl /usr/local/bin/kubectl
```
配置
在控制台的集群列表中找到目标集群后，下载对应的配置文件：kubectl.conf 并将配置文件放置在kubectl的默认路径
```
mv kubectl.conf ~/.kube/config
```