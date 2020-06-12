![docker简单流程图](./img/docker-flow-chart.png)



## CentOS Docker安装

### 卸载旧版本

```bash
sudo yum remove docker \
                  docker-client \
                  docker-client-latest \
                  docker-common \
                  docker-latest \
                  docker-latest-logrotate \
                  docker-logrotate \
                  docker-engine
```

### 安装 Docker Engine-Community

#### 使用Docker仓库进行安装

在新主机上首次安装 Docker Engine-Community 之前，需要设置 Docker仓库。之后，您可以从仓库安装和更新Docker。

#### 设置仓库

安装所需的软件包。yum-utils 提供了 yum-config-manager ，并且 device mapper 存储驱动程序需要 device-mapper-persistent-data 和 lvm2。

```bash
sudo yum install -y yum-utils \
  device-mapper-persistent-data \
  lvm2
```

使用以下命令来设置稳定的仓库。

```bash
sudo yum-config-manager \
    --add-repo \
    https://download.docker.com/linux/centos/docker-ce.repo
```

### 安装 Docker Engine-Community

安装最新版本的 Docker Engine-Community 和 containerd，或者转到下一步安装特定版本：

```bash
sudo yum install docker-ce docker-ce-cli containerd.io
```

### 启动 Docker

```bash
sudo systemctl start docker
```

### 验证是否安装成功

通过运行 hello-world 映像来验证是否正确安装了 Docker Engine-Community 。

```bash
sudo docker run hello-world
```

