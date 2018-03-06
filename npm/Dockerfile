FROM node:alpine

# If you're in China, or you need to change sources, will be set CHANGE_SOURCE to CN in .env.
ENV CHANGE_SOURCE CN
RUN if [ ${CHANGE_SOURCE} == CN ]; then \
        # Change application source from dl-cdn.alpinelinux.org to aliyun source
        echo "change to Chinese apk source"; \
        sed -i 's/dl-cdn.alpinelinux.org/mirrors.aliyun.com/g' /etc/apk/repositories \
    ;fi
# 淘宝镜像有些包安装不了，
# 不翻墙安装chrome driver有问题
# 用HK都话 binding.node 下载很慢
# 用JP都就快；
# 第一次一定要用vpn，安装好后，后面就不用开vpn了（2018.3.1）
#
# RUN if [ ${CHANGE_SOURCE} == CN ]; then \
#         echo "change to Chinese npm source"; \
#         npm config set registry https://registry.npm.taobao.org \
#     ;fi

RUN apk update \
 && apk add --no-cache openssh-client rsync

ENV HOST=0.0.0.0
WORKDIR /var/www/html

# RUN npm install # 编译时候卷不会挂载，所有也没法install

CMD ./node_modules/webpack-dev-server/bin/webpack-dev-server.js --inline --progress --config build/webpack.dev.conf.js --port ${SERVER_PORT}
