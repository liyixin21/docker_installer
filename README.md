# Docker安装
6月以来，大量Docker镜像网站停服，Docker无法下载安装<br>
本仓库用于解决国内网络原因无法安装与使用Docker的问题<br>

### 特点：
- 使用Github Action将官网的安装脚本/安装包定时下载到本项目Release，供国内使用<br>
- 官方安装包，安全可靠<br>
- 每天自动定时同步，保证最新<br>

## 1. Linux安装Docker
一键安装命令（每天自动从官网定时同步）
```
sudo curl -fsSL https://github.com/liyixin21/docker_installer/releases/download/latest/linux.sh| bash -s docker --mirror Aliyun
```

> 备用<br>
```
sudo curl -fsSL https://ghproxy.23250232.xyz/https://github.com/liyixin21/docker_installer/releases/download/latest/linux.sh| bash -s docker --mirror Aliyun
```

启动docker
```
sudo service docker start
```


## 2.Linux配置镜像站

```
sudo vi /etc/docker/daemon.json
```
输入下列内容，最后按ESC，输入 :wq! 保存退出。
```
{
    "registry-mirrors": [
        "https://docker.23250232.xyz/",
    ]
}
```
重启docker
```
sudo service docker restart
```
# 鸣谢
本项目基于 [tech-shrimp/docker_installer](https://github.com/tech-shrimp/docker_installer) 修改开发