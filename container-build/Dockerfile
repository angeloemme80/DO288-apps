# Use the httpd-parent image as base
FROM quay.io/redhattraining/httpd-parent

LABEL io.k8s.description="Platform for building miohttpd" \
      io.k8s.display-name="builder httpd" \
      io.openshift.expose-services="8080:http" \
      io.openshift.tags="builder,httpd"

RUN sed -i "s/Listen 80/Listen 8080/g" /etc/httpd/conf/httpd.conf

EXPOSE 8080

RUN chgrp -R 0 /run/httpd /etc/httpd/ /var/www/html /etc/httpd/logs && chmod -R g=u /run/httpd /etc/httpd/ /var/www/html /etc/httpd/logs

USER 1001


