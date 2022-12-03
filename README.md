# 114-query-system-dependencies

## 说明

该项目存储了智能114系统的相关依赖的docker，打包上传到github中来进行维护

相关博客见：https://yixuan004.github.io/2022/11/26/develop/docker/docker%E4%BD%BF%E7%94%A8/%E5%9F%BA%E4%BA%8EDocker%E8%BF%9B%E8%A1%8C%E9%A1%B9%E7%9B%AE%E9%83%A8%E7%BD%B2-%E4%BB%A5%E6%99%BA%E8%83%BD114%E9%A1%B9%E7%9B%AE%E4%B8%BA%E4%BE%8B/


## nginx

### 配置文件中的相关说明

监听8082端口，和uwsgi通过5002端口通信

### build

```shell
docker build -t 114_nginx:v1 nginx-dockerfile/
```

### run

```shell
docker run -p 8082:8082 -d 114_nginx:v1
```

## redis

### 配置文件中的相关说明

取消bind，然后端口修改为6380（以及一系列安全规范设置），然后关掉daemonize取消后台运行

### build

```shell
docker build -t 114_redis:v1 redis-dockerfile/
```

### run

```shell
docker run -p 6380:6380 -d 114_redis:v1
```