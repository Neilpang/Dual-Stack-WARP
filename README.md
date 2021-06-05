# Dual-Stack-WARP
基于 Docker容器 的WARP 双栈出网

# Docker 成品包
https://hub.docker.com/repository/docker/blueskyxn/dual-stack-warp

## 公网库地址

blueskyxn/dual-stack-warp:1.0

也可以用命令

docker pull docker.io/blueskyxn/dual-stack-warp:1.0

这样就能GET镜像了

运行

docker run --restart=always -itd --name warp-docker --sysctl net.ipv6.conf.all.disable_ipv6=0 --privileged --cap-add net_admin --cap-add sys_module -p 14888:888 -v /etc/warp-docker:/usr/local/etc/v2ray -v /var/log/warp:/var/log/v2ray -v /etc/wg-docker:/etc/wireguard -v /lib/modules:/lib/modules blueskyxn/dual-stack-warp:1.0
