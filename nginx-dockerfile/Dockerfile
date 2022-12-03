FROM nginx:latest

MAINTAINER LiuYixuan

ADD ./ /usr/src/nginx

WORKDIR /usr/src/nginx

RUN \

    # 更新apt的镜像源，并安装一些常用依赖（后续可以取消）
    sed -i s@/deb.debian.org/@/mirrors.aliyun.com/@g /etc/apt/sources.list && \
    apt-get clean && \
    apt-get update && \
    apt-get install vim -y && \
    apt-get install unzip && \
    apt-get install tar && \
    apt-get install procps -y && \
    
    # nginx
    cp /usr/src/nginx/nginx.conf /etc/nginx/nginx.conf && \
    mkdir /var/log/nginx/logs && \
    touch /var/log/nginx/logs/access.http.log && \

    # 查看
    pwd

EXPOSE 8082

# 卡到bash运行=
# CMD ["/bin/bash"]

CMD ["nginx", "-g", "daemon off;"]

# docker build -t 114_nginx:v1 .
# docker run -p 8082:8082 -it 114_nginx:v1
# docker run -p 8082:8082 -d 114_nginx:v1
