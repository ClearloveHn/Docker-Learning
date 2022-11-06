# Learning-Docker
Docker学习

## 1.镜像和容器
1. 镜像是一个可读的文件或文件夹。  
2. 容器是镜像运行的实体。  

## 2.Docker架构
**Docker 客户端:** 用户与 Docker 服务端交互的方式，包括 docker 命令，REST API，各种语言的 SDK。

**Docker 服务端:** 负责响应和处理来自 Docker 客户端的请求，然后将客户端的请求转化为 Docker 的具体操作。例如镜像、容器、网络和挂载卷等具体对象的操作和管理。

**runc(低级容器运行时):** runc 是 Docker 官方按照 OCI 容器运行时标准的一个实现。通俗地讲，runC 是一个用来运行容器的轻量级工具，是真正用来运行容器的。

**containerd(高级容器运行时):** containerd是 Docker 服务端的一个核心组件，它是从dockerd中剥离出来的 ，它的诞生完全遵循 OCI 标准，是容器标准化后的产物。containerd通过 containerd-shim 启动并管理 runC，可以说containerd真正管理了容器的生命周期。
![image](https://camo.githubusercontent.com/20a61d9135e516baabace4960c5fb2d65eca1fa34e1db796cadd7a724a90d203/68747470733a2f2f6368656e677a773235382e6f73732d636e2d6265696a696e672e616c6979756e63732e636f6d2f41727469636c652f32303232303733303039353933392e706e67)

## 3.Docker镜像操作
1. 拉取镜像
```
docker pull 镜像名称[:版本号]
```
2. 删除镜像
```
docker rmi 镜像ID
```
3. 查看本地镜像
```
docker images
```
4. 修改镜像名称
```
docker tag 镜像id 新镜像名称:版本
```
## 4.Docker容器操作
1. 创建并运行容器
```
docker run
-it 交互
-d  后台
-p  端口映射
-v  磁盘挂载

举例:
docker run -d -p宿主机端口∶容器端口 --name 容器名称 镜像的标识(镜像ID)  //本地镜像创建容器
docker run -it --name 容器名称 镜像ID
```
2. 启动已中止的容器
```
docker start 容器ID
```
3. 关闭容器
```
docker stop 容器ID
```
4. 查看容器
```
docker ps //查看目前开启的容器有哪些
docker ps -a //查看有哪些容器
```
5. 进入容器
```
docker exec -it 容器id bash
```
