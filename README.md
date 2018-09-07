# docker 开发环境 for webpack

- 运行webpack的环境
- 使用 alpine，体积小
- 已经安装rsync工具，方便同步文件到远程服务器


## 添加
```shell
git submodule add https://github.com/goodwong/docker-webpack.git .docker-compose
# git submodule add git@github.com:goodwong/docker-webpack.git .docker-compose
cd .docker-compose
cp .env.example .env
```

配置`.env`
SERVER_PORT=8080
COMPOSE_PROJECT_NAME=APP_NAME


## 使用
```shell
cd .docker-compose
docker-compose up -d
docker-compose exec npm sh
# 第一次使用需要安装packages
npm install
# 启动服务
npm run dev # 或者 npm run serve，看webpack版本
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
npm run build
```
