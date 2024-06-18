FROM node:14-alpine3.12

#******************更换Alpine源为mirrors.ustc.edu.cn******************
RUN echo http://mirrors.ustc.edu.cn/alpine/v3.12/main > /etc/apk/repositories \
    && echo http://mirrors.ustc.edu.cn/alpine/v3.12/community >> /etc/apk/repositories

# localtime
RUN apk update \
    && apk add --no-cache vim git g++ make rsync curl autoconf openssh-client tzdata \
    && ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
    && echo "Asia/Shanghai" > /etc/timezone 
