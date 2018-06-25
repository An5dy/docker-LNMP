# 官方版本
FROM nginx:latest

# nginx 默认配置文件
COPY nginx.conf /etc/nginx/nginx.conf
# 多站点配置文件
COPY conf.d/* /etc/nginx/conf.d
# 创建工作目录
RUN mkdir /www

# 容器运行端口
EXPOSE 80
# 匿名卷
VOLUME [ "/www" ]
