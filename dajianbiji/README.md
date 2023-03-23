# 搭建属于的发卡小店-独角数卡

## 搭建属于的发卡小店-独角数卡

## 一、首先给出大佬的 Git官方仓库

```
https://github.com/assimon/dujiaoka
```

我选用的是docker版本的部署,至于为什么选择这个,当然是因为方便!

## 二、直接运行docker版本的独角卡命令

### 1.部署脚本

```c
docker run -dit --name dujiaoka -p 80:80 -p 9000:9000 -e WEB_DOCUMENT_ROOT=/app/public jiangjuhong/dujiaoka
```

### 2.安装的时候需要MySQL和Redis,所以就直接安装他们

```c
docker run -d -p 3306:3306  -e MYSQL_ROOT_PASSWORD=123456 --name mysql -v /data/mysql/config/my.cnf:/etc/mysql/my.cnf -v /data/mysql/db:/var/lib/mysql mysql:5.7

docker run -d --name myredis -p 6379:6379 redis --requirepass "123456"
```

### 没有报错的情况,就已经准备工作好了

### 3.直接访问部署服务的IP,就可以填写对应的MySQL和Redis的信息进行安装,如果数据库没有创建库,你可以通过数据库连接工具创建一个库

### 5.可以使用CF域名管理映射到对应vps的IP上面就可以通过域名进行访问

### 6.里面的邮箱配置可以参考如下图:

![](https://cdn.staticaly.com/gh/VowSir/image-hosting@master/20230323/9b58b8831c1b487d90f8ff452017d619.4q0cbdia2d20.webp)

