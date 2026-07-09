# 基础镜像优化建议版本
FROM node:22.23.1-alpine3.23

# 更换Alpine源为mirrors.ustc.edu.cn
RUN echo http://mirrors.ustc.edu.cn/alpine/v3.23/main > /etc/apk/repositories \
    && echo http://mirrors.ustc.edu.cn/alpine/v3.23/community >> /etc/apk/repositories

# 安装必需的运行时依赖和构建工具
# 如果不需要编译 native 模块，可以移除 g++ make autoconf python3
RUN apk update \
    && apk add --no-cache \
       git \
       g++ \
       make \
       autoconf \
       python3 \
       curl \
       tzdata \
    && ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
    && echo "Asia/Shanghai" > /etc/timezone

# 安装 pnpm
RUN npm install -g pnpm
