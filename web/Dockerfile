FROM nginx:latest
RUN rm -rf /usr/share/nginx/html/
COPY webfiles/ /usr/share/nginx/html/
RUN rm -rf /etc/nginx/nginx.conf
RUN rm -rf /etc/nginx/conf.d/default.conf
COPY roboshop.conf /etc/nginx/nginx.conf
