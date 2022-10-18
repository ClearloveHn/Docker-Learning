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
