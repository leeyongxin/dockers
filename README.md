# dockers
#### for ipreport
```
# build, where :1 is the version number

docker build -t ipreport:1

# run
docker run -it --rm --name ipreport ipreport:1 aliupdate.py
```
---
# 使用 vbox_websrv 和 phpvirtualbox 的docker 来管理 docker
sudo docker run --name vbox_http --restart=always \
    -p 80:80 \
    -e svr1_HOSTPORT=192.168.194.83:5678\
    -e sv1_NAME=serverName \
    -e 1_USER=yongxin \
    -e 1_PW=123456 \
    --network="host" \
    -e CONF_browserRestrictFolders="/data,/home" \
    -d jazzdd/phpvirtualbox

# vbox 是host上属于 vboxusers组的一个用户， 需要有路径/home/vbox
sudo docker run -it --name=vbox_websrv_1 --restart=always --network="host" jazzdd/vboxwebsrv vbox@192.168.194.83
