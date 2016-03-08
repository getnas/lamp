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

#### 关于 `www` 程序根目录

`PHP` 和 `Apache` 默认以 `www-data` 用户(组)身份运行网站程序，如果你使用本项目作为开发环境，即需要在主机上对 `www` 目录中的代码进行编辑，则需要做适当权限设置。

> 假设当前主机用户为 `ubuntu`

    # 将 `ubuntu` 添加到 `www-data` 组
    usermod -aG www-data ubuntu
    # `www` 目录修改为组成员可执行
    chmod g+x ./www/

> 设置完毕，当前用户需要注销并重新登陆。

#### 注意事项

如果要在同一主机运行多个需要映射 `80` 端口的容器时，请结合 [Docker Nginx Reverse](https://github.com/getnas/nginx-reverse) 使用。
