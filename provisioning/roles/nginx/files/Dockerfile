FROM nginx
MAINTAINER Quentin McRee version: 0.1
COPY ["rendered_nginx.conf", "/etc/nginx/"]
EXPOSE 80 443
CMD ["nginx", "-g", "daemon off;"]