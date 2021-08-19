# mysql-docker
快速启动 mysql 测试服务。

> Windows 平台 请把 ${PWD} 替换为具体路径
> Windows 平台 请替换 cluster 文件夹中路径
> Windows 平台 如果在 wsl 环境下执行则不需要替换

## 启动一个 mysql 映射到 3306 端口
```
docker run -p 3306:3306 --name mysql_main \
-v ${PWD}/main/conf:/etc/mysql \
-v ${PWD}/main/files:/var/lib/mysql-files \
-v ${PWD}/main/logs:/var/log/mysql \
-v ${PWD}/main/data:/var/lib/mysql \
-e MYSQL_ROOT_PASSWORD=123456 \
-d mysql
```

## 启动一个 mysql 映射到 3307 端口
```
docker run -p 3307:3306 --name mysql_master \
-v ${PWD}/master/conf:/etc/mysql \
-v ${PWD}/master/files:/var/lib/mysql-files \
-v ${PWD}/master/logs:/var/log/mysql \
-v ${PWD}/master/data:/var/lib/mysql \
-e MYSQL_ROOT_PASSWORD=123456 \
-d mysql
```


## 启动一个 mysql 集群 映射到 3306 端口
```
# 进入文件夹
cd cluster
# 前端运行
docker-compose up
# 后端运行
docker-compose up -d
```
