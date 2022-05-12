FROM nginx:latest

LABEL "author"="Left Bank Inc"

# 复制发布的文件，部署到Docker镜像容器
COPY dist/  /etc/nginx/html/ui
COPY nginx.conf /etc/nginx/nginx.conf
RUN echo 'mCloud UI Console image build completed'
