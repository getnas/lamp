## Docker LAMP

本项目使用 php:7-apache 和 mariadb 官方镜像构建。

#### 使用方法：

```
git clone https://github.com/getnas/lamp.git .
cd lamp
# 根据需要修改相关配置，然后启动项目。
docker-compose up -d

```

默认开放 80 端口，浏览器访问 http://localhost

MariaDB 数据库账户 `root`，初始密码 `123456`

#### 注意事项

如果要在同一主机运行多个需要映射 `80` 端口的容器时，请结合 [Docker Nginx Reverse](https://github.com/getnas/nginx-reverse) 使用。
