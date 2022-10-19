FROM redhat/ubi8:8.5

LABEL maintainer="Victoria Gomes <vicgstudies@gmail.com>"

RUN yum install -y httpd && yum clean all

COPY /src /var/www/html/

ENV PORT 8080

EXPOSE 8080

RUN sed -ri -e "/^Listen 80/c\Listen ${PORT}" /etc/httpd/conf/httpd.conf && \ 
    chown -R apache:apache /etc/httpd/logs/ && \ 
    chown -R apache:apache /run/httpd/

CMD ["httpd", "-D", "FOREGROUND"]

