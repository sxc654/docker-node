FROM alpine:3.19

#******************更换Alpine源为mirrors.ustc.edu.cn******************
RUN echo http://mirrors.ustc.edu.cn/alpine/v3.19/main > /etc/apk/repositories \
    && echo http://mirrors.ustc.edu.cn/alpine/v3.19/community >> /etc/apk/repositories

# localtime
RUN apk update \
    && apk add --no-cache tzdata \
    && ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
    && echo "Asia/Shanghai" > /etc/timezone 

RUN apk update \
    && apk add --no-cache gcc g++ libgcc make rsync vim git curl autoconf openssl openssh-client bash ca-certificates ncurses coreutils python3 linux-headers grep util-linux binutils findutils

    
ENV NVM_DIR=/root/.nvm

# Install nvm with node and npm
RUN curl https://raw.githubusercontent.com/creationix/nvm/v0.39.1/install.sh | bash \
    && echo 'export NVM_DIR="$HOME/.nvm"' >> ~/.bash_profile \
    && echo '[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"' >> ~/.bash_profile \
    && echo '[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"' >> ~/.bash_profile \
    && source $NVM_DIR/nvm.sh \
    && nvm install 18.14.0 \
    && nvm install 17.14.0 \
    && nvm install 14.14.0 \
    && nvm use 18.14.0
