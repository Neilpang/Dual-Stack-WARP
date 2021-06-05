# Dual-Stack-WARP
基于 Docker容器 的WARP 双栈出网

教程：https://www.blueskyxn.com/202106/4629.html

# Docker HUB
https://hub.docker.com/repository/docker/blueskyxn/dual-stack-warp

## 公网库地址

blueskyxn/dual-stack-warp:1.0

也可以用命令

docker pull docker.io/blueskyxn/dual-stack-warp:1.0

这样就能GET镜像了

## 利用镜像部署

运行容器

docker run --restart=always -itd --name warp-docker --sysctl net.ipv6.conf.all.disable_ipv6=0 --privileged --cap-add net_admin --cap-add sys_module -p 14888:888 -v /etc/warp-docker:/usr/local/etc/v2ray -v /var/log/warp:/var/log/v2ray -v /etc/wg-docker:/etc/wireguard -v /lib/modules:/lib/modules blueskyxn/dual-stack-warp:1.0


进去容器SSH

docker exec -it warp-docker /bin/bash

运行程序
nohup /usr/local/bin/v2ray -config /usr/local/etc/v2ray/config.json &

然后自己修改配置/反代等操作自己玩吧

### 参考参数
<details><summary>参考参数</summary>
AID：4
  
Path：/api
  
port:888/443
  
uuid:4c0411ac-158e-4d66-a810-90bd2389b84c
  
network:ws
</details>



