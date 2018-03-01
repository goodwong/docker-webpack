# docker 开发环境 for webpack

- 运行webpack的环境


## 添加

./docker-compose

## 使用
```shell
cd ./docker-compose
cp .env.example .env
docker-compose up -d
```

访问
http://localhost:端口 （端口需要在.env文件配置，默认8080）

### 首次使用
需要VPN！
需要VPN！
需要VPN！

因为淘宝镜像有点问题，需要VPN安装npm包

### 日常操作
```shell
docker-compose exec npm sh
```
进入容器后，愉快的运行命令吧
```shell
./deploy.sh prod
```

## 配置.env
SERVER_PORT=8080
