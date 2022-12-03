FROM redis:6.2

MAINTAINER LiuYixuan

ADD ./ /home/redis1

WORKDIR /home/redis1

RUN \

    # 更新apt的镜像源，并安装一些常用依赖（后续可以取消）
    sed -i s@/deb.debian.org/@/mirrors.aliyun.com/@g /etc/apt/sources.list && \
    apt-get clean && \
    apt-get update && \
    apt-get install vim -y && \
    apt-get install unzip && \
    apt-get install tar && \
    apt-get install procps -y && \
    
    # 查看
    pwd

EXPOSE 6380

CMD ["/usr/local/bin/redis-server", "/home/redis1/redis.conf"]
# CMD ["/bin/bash"]

# cd /data/sdb2/lyx/_114/redis-dockerfile
# docker build -t 114_redis:v1 .

# TODO docker compose的时候，挂载的方式redis.conf

# docker run -p 6380:6380 -it 114_redis:v1
# docker run -p 6380:6380 -d 114_redis:v1

# /usr/local/bin/redis-server /home/redis1/redis.conf