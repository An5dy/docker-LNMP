# docker-LNMP
### 第一步：设置配置文件
``
cp variables.env.example variables.env
``

设置数据库初始密码、测试库及新增用户

### 第二步：设置 php、mysql、nginx 配置文件
具体文件在相应的文件夹下

### 第三步：构建服务容器
``
docker-compose build
``

### 第四步：运行
``
docker-compose up 或 -d（后台运行）
``

- 停止运行

``
docker-compose down
``

### 第五步：测试
访问 127.0.0.1:81，查看 phpinfo 信息，模块是否安装成功。


